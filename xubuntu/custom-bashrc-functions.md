```bash
cr() {
  if [ "$1" = "e" ]; then
    cd ~/exercism/crystal
  elif [ "$1" = "t" ]; then
    if [ "$2" = "--day" ]; then
      day=$3
      crystal day${day}_*test.cr
    else
      crystal *test.cr
    fi
  elif [ "$1" = "s" ]; then
    exercism submit | ls src/*.cr
  else
    crystal "$@"
  fi
}

rb() {
  if [ "$1" = "e" ]; then
    cd ~/exercism/ruby
  elif [ "$1" = "t" ]; then
    if [ "$2" = "--day" ]; then
      day=$3
      ruby day${day}_*test.rb
    else
      ruby *test.rb
    fi
  elif [ "$1" = "s" ]; then
    exercism submit | ls *.rb | grep -v test
  elif [ "$1" = "--day" ]; then
    day=$2
    for file in day${day}_*.rb; do
      if ! grep -qE "others_solution|test" "$file"; then
        ruby "$file"
      fi
    done
  else
    ruby "$@"
  fi
}

exer() {
  if [ "$1" = "gc" ]; then
    if [ "$2" = "--dry-run" ]; then
      echo "Showing the file that will be removed..."
      echo

      ls ~/exercism/*/*
    else
      rm -fr exercism/*
    fi
  else
    exercism "$@"
  fi
}
```
