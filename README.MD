#### cambiar \ a / en windows, desde el clipboard a clipboard

```R
writeClipboard(gsub("\\\\", "/", readClipboard()))
```
