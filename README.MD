#### cambiar \ a / en windows, desde el clipboard a clipboard

```R
writeClipboard(gsub("\\\\", "/", readClipboard()))
```

#### limpia ambiente y variables antes de ejecutar un código. 
```R
gc()                        # ejecuta garbage collection
rm(list=ls())               # limpiar ambiente
cat('\014')                 # limpiar consola
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
    

# comparacion ciclo
library(doParallel)
cl <- makeCluster(4)
registerDoParallel(cl)

tempMes <- function(TE, TJ, Dias = c(15, 45, 75, 105, 135, 165, 195, 225, 255, 285, 315, 345)) {
    tMes <- rep(NA, times = length(Dias))

    for (count in 1:length(Dias)) {
        Dia <- Dias[count]
        tMes[count] <- TE - ((1 - sin(.0174533 * (70 + Dia))) * (TE - TJ) * .5) - .5 * ((sin(.0174533 * (Dia - 180))))
    }

    return(tMes)
}

foreach(txe, txj, .combine = rbind) %dopar% tempMes(txe, txj)

stopCluster(cl)



```
