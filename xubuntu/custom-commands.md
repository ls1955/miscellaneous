```
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

```