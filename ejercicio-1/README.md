# dev-pec2 - Módulo 3 Diseño y desarrollo

## EJERCICIO 1

**Adquiera un dominio bajo el TLD ‘.test’ en la testnet que desee (Rinkeby o Ropsten).  Si   no   le   es   posible   sincronizar   un   nodo,   puede   desplegar   el   servicio   ENS   en   la   red   testrpc con Geth. Describa el procedimiento seguido.** 

---

**1. Intentos sincronización con Rinkeby, Ropsten y testRPC** 

Para sincronizar con las redes de Rinkeby y Ropsten he utilizado el cliente de Geth: 

`geth --rinkeby`
`geth --ropsten`

Mientras inicializaba la sincronización me bajé del repositorio de ENS en GIT HUB (ens-master.zip). Del repositorio copié el archivo ensutils-testnet.js donde realicé los siguientes cambios para trabajar en Rinkeby:

`contract address: 0xe7410170f87102df0055eb195163a03b7f2bff4a (line 220)`
`publicResolver address: 0x5d20cf83cb385e06d2f2a892f9322cd4933eacdc (line 1314)`

Una vez hechos los cambios en las líneas del archivo ensutils-testnet.js. EMpecé a usar la consola de Ethereum con las siguientes instrucciones:

`Ropsten: geth --testnet attach`
`Rinkeby: geth --rinkeby attach`

Una vez abierta la consola de Ethereum cargué el archivo ensutils-testnet.js:

![Lazamiento archivo ens](https://github.com/anakb/dev-pec2/blob/master/ejercicio-1/ensutils%20carga%20consola.png "Lazamiento archivo ens")

Tras el lanzamiendo desbloquee mi cuenta indicando una password. 

Una vez desbloqueada la cuenta, el saldo en mi address se mantuvo a cero a pesar de recibir ethers en las correspondientes cuentas de Ropsten y Rinkeby:

![Adress a cero a pesar de recibir eth](https://github.com/anakb/dev-pec2/blob/master/ejercicio-1/No%20gas.png "Lazamiento archivo ens")

Para comprobar el saldo de mi address 0x2623b1a0A95325d996F1F3B1da945731ad2d72CD (en Ropsten): 

https://ropsten.etherscan.io/tx/0x9efb915f26ee4f716456644f55af98310e0374cb8b70163ca7dca5460c7a36a1

Para comprobar el saldo de mi address 0x5940F6555F74B4Ca254078673cD5AB7FDB6404A7 (en RInkeby)

Ante la imposibilidad de conseguir que se reflejen los ethers en las dos opciones, Rinkeby y Ropsten, finalmente tuve que hacer la prueba con la red testrpc. 


---

**2. Prueba en testRPC**

Para utilizar rpc tuve que descargar e instalar rpc en mi ordenador.

`npm install -g ethereumjs-testrpc`

Después lancé el cliente Geth con testrpc 

`geth --dev --rpc --mine`

Una vez lanzada la conexión con la red, en la consola de Ethereum indiqué lo siguiente:

`geth --datadir /tmp/ --ipcpath /tmp/geth.ipc attach`

![Consola con RPC](https://github.com/anakb/dev-pec2/blob/master/ejercicio-1/consola%20con%20rpc.png "Consola con RPC")

En esa pantalla, para mi address tenía eth suficientes para continar con el ejercicio de ENS.

Para continuar solicité la comprobación de si mi nombre estaba registrado pero me salió el error "invalid address", pero no he tenido forma de encontrar la address que corresponda a la testnet de rpc:

![Error "invalid address"](https://github.com/anakb/dev-pec2/blob/master/ejercicio-1/Fallo%20en%20address%20RPC.png "Error invalid address")

Lo que sí me permitió la consola es establecer un Resolver e indicarme el public Resolver como se puede ver en la imagen anterior. 


