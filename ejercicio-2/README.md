# dev-pec2 - Módulo 3 Diseño y desarrollo

## EJERCICIO 2

**IPFS** 
---

**1. Hacer pequeña modificación en proyecto pet-shop**

He cambiado `Pete` por `Ana` en el fichero `index.html`.

![pantalla-ej2-01.png](https://github.com/anakb/dev-pec2/blob/master/Ejercicio%202/1.png "pantalla-ej2-01")
---

**2. Subir proyecto pet-shop modificado a github (sin incluir node_modules)**

Para que la carpeta `node_modules` no se incluya, en la raiz del proyecto pet-shop incluyo el fichero `.gitignore` con la linea `node_modules`.

```
git add index.html
git commit "Little changes in index.html (show my name)"
git push -u origin master
```

![pantalla-ej2-02.png](https://github.com/anakb/dev-pec2/blob/master/Ejercicio%202/2.png "pantalla-ej2-02")
---

**3. Instalacion IPFS**

Descargar el binario de [https://dist.ipfs.io/#go-ipfs](https://dist.ipfs.io/#go-ipfs)

Seguir las instrucciones de instalacion de [https://docs.ipfs.io/introduction/install](https://docs.ipfs.io/introduction/install)

```
cd ~/Descargas
tar xvfz go-ipfs_v0.4.17_linux-amd64.tar.gz
cd go-ipfs
sudo ./install.sh
```

![pantalla-ej2-03.png](https://github.com/anakb/dev-pec2/blob/master/Ejercicio%202/3.png "pantalla-ej2-03")
---

**4. Inicialización de daemon y subida de archivos a IPFS**

Para empezar a usar IPFS se inicializa el daemon:

`ipfs daemon`

![pantalla-ej2-04.png](https://github.com/anakb/dev-pec2/blob/master/Ejercicio%202/4.png "pantalla-ej2-04")

Despues, en otra terminal, se sube el directorio de la dApp a IPFS:

`ipfs add -r pet-shop`

![pantalla-ej2-05.png](https://github.com/anakb/dev-pec2/blob/master/Ejercicio%202/4.png "pantalla-ej2-05")

El hash de ese directorio es: QmNgwtUffRGB9JeEkhgooEQxsXDHCdNyJPULEKybC99yGK 
Comprobamos que con ese hash se puede obtener el directorio en IPFS. 