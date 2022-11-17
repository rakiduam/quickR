#### cambiar \ a / en windows, desde el clipboard a clipboard

```R
writeClipboard(gsub("\\\\", "/", readClipboard()))
```

#### limpia ambiente y variables antes de ejecutar un código. 
```R
rm ( list = ls () )
cat( rep ( "\n", 64 ) )
```
#### listado de archivos en una carpeta, por tipo
```R
setwd(dir)
files = list.files ( pattern = 'hdf$' ) 
```
#### comprension de listas
```R
library(foreach)
foreach(x=1:length(x_var), .combine = rbind) %do% (x_var[x])^2

# list comprehension tipo python
foreach(x = sample(1:10000, 10), .combine = c) %:%
    when(x %% 3 == 0 || x %% 5 == 0) %do% x

```
