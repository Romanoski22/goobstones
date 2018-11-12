# goobstones/*Ejercicio 2
Utilizando el tipo Persona (práctica de registros), realice las siguientes funciones,
suponiendo que no hay dos personas con el mismo número de DNI, donde usamos el tipo
padrón como renombre de listas de personas:
1. perteneceDNI(padrón, dni), recibe un padrón y un número de DNI y describe verdadero si
hay una persona con dicho DNI en el padrón.
3. convivientes(padrón, domicilio), recibe un padrón y un domicilio y describe todas
las personas que viven en dicho domicilio.
4. sinPersonaConDNI(padrón, dni), recibe un padrón y un número de DNI y describe el
padrón que se obtiene de sacar a la persona con dicho DNI.
5. sinPersonasConDNI(padrón, dnis), recibe un padrón y una lista con números de DNI y
describe el padrón que resulta de eliminar todas las personas correspondientes a los DNIs
pasados como parámetro.
6. nuevosDatosPersona(padrón, dniViejo, persona), recibe un padrón, un dni y una
persona y retorna el padrón que se obtiene de actualizar los datos de la persona con el dni
viejo para que coincidan con la nueva persona. En otras palabras, debe eliminarse aquella
persona del padrón correspondiente al dni viejo, y agregarse la nueva persona*/


/*Declarar el registro Persona, que contenga el número de DNI, el domicilio es un String y un
booleano indicando si la persona es de sexo masculino. Implementar las siguientes funciones:*/

type Persona is record {
    field dni //numero
    field domicilio // string
    field masculino //booleano
}

function perteneceDNI(padrón, dni) {
    listaAux := padrón
    while (not(esVacía(listaAux)) && dni /= dni(primero(listaAux))){
    listaAux:= resto(listaAux)
    }
    return (not(esVacía(listaAux)))
}


/**program {
    p1:=Persona(dni<-1,domicilio<-"calle1",masculino<-True)
    p2:=Persona(dni<-2,domicilio<-"calle2",masculino<-True)
    p3:=Persona(dni<-3,domicilio<-"calle3",masculino<-True)
    p4:=Persona(dni<-4,domicilio<-"calle4",masculino<-True)
    p5:=Persona(dni<-5,domicilio<-"calle5",masculino<-True)
    p6:=Persona(dni<-6,domicilio<-"calle6",masculino<-True)
    padrón1:=[p1,p2,p3,p4,p5,p6]

    
    return(perteneceDNI(padrón1, 6))
}

function persona1() {
    return (Persona(dni<-1,domicilio<-calle1,masculino<-True))
}**/

/*2. personaConDNI(padrón, dni), recibe un padrón y un número de DNI y describe la primer
Persona que tenga el DNI indicado. Puede suponer que existe alguna persona con dicho
DNI.*/

function personaConDNI(padrón, dni){
    padrónAux:=padrón
    while(dni /= dni(primero(padrónAux))){
        padrónAux:= resto(padrónAux)
    }
    return(primero(padrónAux))
}

function persona1() {
    return (Persona(dni<-1,domicilio<-"calle1",masculino<-True))
}

function persona2() {
    return (Persona(dni<-2,domicilio<-"calle3",masculino<-True))
}

function persona3() {
    return (Persona(dni<-3,domicilio<-"calle3",masculino<-True))
}

function persona4() {
    return (Persona(dni<-4,domicilio<-"calle4",masculino<-True))
}

function persona5() {
    return (Persona(dni<-5,domicilio<-"calle5",masculino<-True))
}

function persona6() {
    return (Persona(dni<-6,domicilio<-"calle6",masculino<-True))
}

function padron1(){
    return([persona1(),persona2(),persona3(),persona4(),persona5(),persona6()])
}

/**program {
    return(personaConDNI(padron1(), 4))
}**/

/*3. convivientes(padrón, domicilio), recibe un padrón y un domicilio y describe todas
las personas que viven en dicho domicilio.*/

function convivientes(padrón, domicilio){
    convivientes:=[]
    foreach persona in padrón {
        if(domicilio(persona) == domicilio){
           convivientes:= convivientes ++ [persona] 
        }
    }
    return(convivientes)
}

/**program {
    return(convivientes(padron1(), "calle3"))
}**/

/*4. sinPersonaConDNI(padrón, dni), recibe un padrón y un número de DNI y describe el
padrón que se obtiene de sacar a la persona con dicho DNI.*/

function sinPersonaConDNI(padrón, dni){
    nuevopadron:=[]
    foreach persona in padrón {
        if (dni(persona) /= dni) &&  {
            nuevopadron:= nuevopadron ++ [persona]
        } 
    }
    return (nuevopadron)
}

/**program {
    return ( sinPersonaConDNI(padron1(), 4))
}**/

/*5. sinPersonasConDNI(padrón, dnis), recibe un padrón y una lista con números de DNI y
describe el padrón que resulta de eliminar todas las personas correspondientes a los DNIs
pasados como parámetro.*/

function 

function sinPersonasConDNI(padrón, dni){
    nuevopadron:=[]
    foreach persona in padrón {
        if (dni(persona) /= dni){
            nuevopadron:= nuevopadron ++ [persona]
        } 
    }
    return (nuevopadron)
}

/**program {
    return ( sinPersonasConDNI(padron1(), 4))
}**/



