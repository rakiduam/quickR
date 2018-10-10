#### copiar directorio desde el clipboard
```R
writeClipboard(gsub("\\\\", "/", readClipboard()))
```
