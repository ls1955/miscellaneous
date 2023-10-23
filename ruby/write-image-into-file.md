Open the file in `wb` mode before writing image content

```Ruby
# bad, won't write the content as expected
File.open("image.jpg", "w") { |img| img.write content }

# good
File.open("image.jpg", "wb") { |img| img.write content }
```
