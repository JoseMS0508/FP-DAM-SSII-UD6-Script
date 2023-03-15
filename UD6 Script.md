```bash
# EJERCICIO 1

read -p "Introduce un número: " num

if (("$num" >= "0"))
then
    echo "Es positivo"
else 
    echo "No es positivo"
fi


# EJERCICIO2
read -p "Introduce un número: " num

if (("$num" < "0"))
then
    echo "Es negativo"
else 
    echo "No es negativo"
fi

# EJERCICIO3
read -p "Introduce un numero: " num
if [[ "$num" -eq "0" ]]
then
    echo "ES cero"
else 
    echo "NO es cero"
fi

# EJERCICIO 4
read -p "Introduce un numero: " num
if (("$num" > "0"))
then
    echo "ES positivo"
elif (("$num" < "0"))
then
    echo "ES negativo"
elif [[ "$num" -eq "0" ]]
then
    echo "ES cero"
fi


# EJERCICIO 5
if [[ "$#" -eq "3" ]] 
then 
    echo "Se han pasado tres parametros"
else 
    echo "ERROR: El numero de parametros usados != 3" 
fi

# EJERCICIO 6
VAR1=$1
VAR2=$2
VAR3=$((VAR1 + VAR2))
if [[ "$#" -eq "2" ]] 
then 
    echo "El resultado de la suma de los parametros es: $VAR3"
else 
    echo "ERROR: El numero de parametros usados != 2" 
fi

# EJERCICIO 7
VAR1=$1
VAR2=$2
VAR3=$3
if [[ "$#" -eq "3" ]] 
then 
    echo "Se han pasado tres parametros"
    if [[ $VAR3 == "+" ]]
    then 
        echo "El resultado de la SUMA de los parametros es: $((VAR1 + VAR2))"
    elif [[ $VAR3 == "-" ]]
    then
        echo "El resultado de la RESTA de los parametros es: $((VAR1 - VAR2))"
    elif [[ $VAR3 == "*" ]]
    then
        echo "El resultado de la MULTIPLICACION de los parametros es: $((VAR1 * VAR2))"
    elif [[ $VAR3 == "/" ]]
    then
        echo "El resultado de la DIVISION de los parametros es: $((VAR1 / VAR2))"
    fi
else 
    echo "ERROR: El numero de parametros usados != 3" 
fi

# EJERCICIO 8
read -p "Introduce la ruta de un fichero: " ruta
if [[ -e "$ruta" ]] 
then 
    echo "El fichero introducido en la ruta SI existe"
else 
    echo "El fichero introducido en la ruta NO existe"
fi

# EJERCICIO 9
read -p "Introduce una ruta: " ruta
if [[ -f "$ruta" ]] 
then 
    echo "La ruta corresponde a un FICHERO"
elif [[ -d "$ruta" ]] 
then
    echo "La ruta corresponde a un DIRECTORIO"
fi

# EJERCICIO 10
read -p "Introduce la ruta de un fichero. Comprobaremos los permisos del mismo (r,w,x): " ruta
if [[ -r "$ruta" ]] 
then 
    echo "El ejecutante del script tiene permiso de LECTURA"
elif [[ -w "$ruta" ]] 
then
    echo "El ejecutante del script tiene permiso de ESCRITURA"
elif [[ -x "$ruta" ]] 
then
    echo "El ejecutante del script tiene permiso de EJECUCION"
fi

# EJERCICIO 11
for ((i=0; i<50; i++))
do 
    echo "Hola"
done

# EJERCICIO 12
for ((i=0; i<10; i++))
do 
    read -p "Introduce una palabra: " palabra
    echo "$palabra"
done

# EJERCICIO 13
for ((i=0; i<$1; i++))
do 
    echo "Hola"
done

# EJERCICIO 14
for ((i=0; i<=$1; i++))
do 
    echo ${i}
done

# EJERCICIO 15
VAR=0
for ((i=1; i<=$1; i++))
do 
    VAR=$(($VAR+$i))
done
echo ${VAR}

# EJERCICIO 16
VAR1=$1
VAR2=$2
AUX=0;
echo "El argumento 1 introducido es: $VAR1"
echo "El argumento 2 introducido es: $VAR2"
AUX=$1
VAR1=$VAR2
VAR2=$AUX
echo "--------INTERCAMBIAMOS LOS VALORES DE LOS PARAMETROS--------"
echo "El argumento 1 ahora es: $VAR1"
echo "El argumento 2 ahora es: $VAR2"

# EJERCICIO 17
VAR=0
interrumpir=":q"
while [[ $VAR -eq 0 ]]
do
    read -p "Introduce un texto: " texto
    if [[ "$texto" == "$interrumpir" ]]
    then
        VAR=1
    fi
done

# EJERCICIO 18
VAR=0
textoIntroducido=""
interrumpir=":q"
while [[ $VAR -eq 0 ]]
do
    read -p "Introduce un texto: " texto
    textoIntroducido+=$texto
    if [[ "$texto" == "$interrumpir" ]]
    then
        VAR=1
        echo $textoIntroducido>archivo.txt
    fi
done


# EJERCICIO 19
VAR=0
interrumpir=":q"
while [[ $VAR -eq 0 ]]
do
    read -p "Introduce un texto: " texto
    echo $texto>>archivo2.txt
    if [[ "$texto" == "$interrumpir" ]]
    then
        VAR=1
    fi
done

# EJERCICIO 20
read -p "Introduce un numero: " num
echo "3">numeros.txt
if grep -q $num numeros.txt; then
    echo "El numero $num SI se encuentra en el archivo numeros.txt"
else 
    echo "El numero $num NO se encuentra en el archivo numeros.txt"
fi
