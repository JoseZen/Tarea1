#Modelo para VRPTW

#Definición de conjuntos

set clientes;
set camiones;

#Definición de parámetros

param hor >= 0;
param setup{clientes, clientesnprima, camiones} >= 0;
#falta modificar el setup
param h{clientes, camiones} >= 0;
param rc{clientes, camiones} >= 0;
param tf{clientes} >= 0;

#Definición de variables


var g{clientes} >= 0;
var o{clientes} >= 0;
var l{camiones} >= 0;
var b{clientes} binary;

#Definición de la función objetivo

minimize tiempodeentrega: sum{n in clientes, c in camiones}b[n]*(rc[n,c] + setup);

#Minimizar el tiempo que tardan los camiones en satisfacer la entrega
#a todos los clientes. (Minimizar el makespan)
#Debido a la modificación del setup, no pude decir que es el tiempo desde
#El cliente n-1 hasta el cliente n, por el camion n HAY QUE MODIFICAR

#Definición de las restricciones

#Cliente debe ser atendido sólo 1 vez
subject to

#Cliente debe ser atendido por sólo 1 camión
subject to

#Cliente debe ser atendido dentro de un bloque horario definido
subject to

#Para cada cliente existe un tiempo de permanencia definido como el
#tiempo necesario para el camión lo atienda

subject to

#Los tiempos de traslado (setup[n,n',c] no se pueden contabilizar como tiempos de entrega

subject to
