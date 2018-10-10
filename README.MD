#### cambiar \ a / en windows, desde el clipboard a clipboard

```R
writeClipboard(gsub("\\\\", "/", readClipboard()))
```

#### limpia ambiente y variables antes de ejecutar un código. 
```
rm ( list = ls () )
cat( rep ( "\n", 64 ) )
```
