# Objetos y Clases en python

- Un objeto es un paradigma en la programación con algunas propiedades como encapsulamiento, herencia, blablablabla..  :-D

## Definiendo objetos en python

Un objeto en python se define mediante la palabra __class nombreDelObjeto:__

Por ejemplo:

```
# Aquí se define el objeto
class Coche:
    def __init__(self):
        # cuando creamos el objeto por PRIMERA vez, tenemos la posibilidad de asignarle algunos atributos (variables propias del objeto)
        self.ruedas = 4
        self.puertas = 5

# Primero creamos el objeto 'micoche' que es del tipo, o de la clase, Coche
# los objetos se crean com si fueran variables
micoche = Coche()

# al crear micoche ya tiene dos atributos por defecto (ojo: esto no es obligatorio de las clases)
print ('Mi coche tiene %d ruedas' %micoche.ruedas)

>> Mi coche tiene 4 ruedas
```

## La palabra __self__

__self__ hace referencia al propio objeto.

Aclaración:

```
class Tomate:
    def __init__(self):
        self.color = 'rojo'
        color = 'verde'

fruta = Tomate()
print fruta.color

>> rojo
```

digamos que python sustituye __self__ -->> __fruta__

```
fruta1 = Tomate()
fruta2 = Tomate()

fruta2.color = 'verde'

# aquí sustituye self -->> fruta1
print fruta1.color
>> rojo

# aquí sustituye self -->> fruta2
print fruta2.color
>> verde
```

## Métodos de objetos

Además de poder definir atributos, se pueden definir __Métodos__, esto es una acción que puede realizar nuestro objeto (más o menos como si fueran funciones que pueden hacer nuestros objetos).

```
class Coche:
    def __init__(self):
        self.ruedas = 4
        self.puertas = 5

        # creo 1 atributo nuevo
        # al crear el objeto coche, el coche está parado inicialmente
        self.encendido = False

    def Estado(self):
        if self.encendido:
            print ('El coche está encendido, puedes moverte')
        else:
            print ('El coche aún está parado, no lo puedes conducir')

    def Arrancar(self):
        # Ahora Coche imprimirá por pantalla un mensaje
        print ('Hemos arrancado motores')
        self.encendido = True

micoche = Coche()

micoche.Estado()
>> El coche aún está parado, no lo puedes conducir

micoche.Arrancar()
>> Hemos arrancado motores

micoche.Estado()
>> El coche está encendido, puedes moverte
```

De la misma forma que podemos usar print, se pueden usar todas las funciones de python

## Pasando parámetros a los métodos

```
class Coche:
    def __init__(self):
        self.ruedas = 4
        self.puertas = 5

        self.encendido = False

        # creo 1 atributo nuevo
        # inicialmente el coche ha recorrido 0 km
        self.kilometros_recorridos = 0

    def Estado(self):
        if self.encendido:
            print ('El coche está encendido, puedes moverte')
        else:
            print ('El coche aún está parado, no lo puedes conducir')

    def Arrancar(self):
        # Ahora Coche imprimirá por pantalla un mensaje
        print ('Hemos arrancado motores')
        self.encendido = True

    def Mover(self, kilometros):
        if self.encendido:
            # si el coche está encendido, aumento los kilometros en lo que se pase por parámetro
            self.kilometros_recorridos += kilometros
        else:
            # si no lo  está, no se puede mover
            print('No puedes mover el coche si no está encendido')

micoche = Coche()

micoche.Estado()
>> El coche aún está parado, no lo puedes conducir

micoche.Arrancar()
>> Hemos arrancado motores

micoche.Estado()
>> El coche está encendido, puedes moverte

micoche.Mover(35)
print ('El coche ha recorrido: %d' % micoche.kilometros_recorridos)
```


## Métodos mágicos:

### '__str__(self)'

Este método es el que se ejecuta cuando se hace print sobre el objeto:

```
class Ultimo:
    def __init__(self):
        self.atributo = 'whatever'

    def __str__(self):
        return self.nombre

ultimoobjeto = Ultimo()
print (ultimoobjeto)

>> whatever
```

Hay muchos más, buscar en google.
