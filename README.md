# Punto 1: Blinky

![](https://github.com/Hitalio/TP1/blob/master/images/main.PNG)

* gpioWrite recibe gpioMap_t y un bool_t, que indican el led que quiero setear y el estado de este (prendido o apagado), respectivamente.

![](https://github.com/Hitalio/TP1/blob/master/images/gpioWrite.PNG)
 
     gpioMap_t -> tipo enumerativo asociado a la EDU-CIAA-NXP. Le pone nombre a los 62 pines. 
     LEDB -> 42 del gpioMap_t   

     *  Se declaran 5 enteros -> pinNamePort, pinNamePin, func, gpioPort, gpioPin
     *  Entra a gpioObtainPinConfig -> Le paso la dirección de memoria de los enteros definidos anteriormente para 
                                       modificarlos.

![](https://github.com/Hitalio/TP1/blob/master/images/gpioObtainPinConfig.PNG)

          * Guardo un valor en los 5 enteros.
          * Guardo los valores que están en el vector gpioPinsConfig en la posición LEDB
                   * Entra a gpioPinsConfig es un vector de tipo pinConfigGpioLpc4337_t, el cuál es de la siguiente forma:

![](https://github.com/Hitalio/TP1/blob/master/images/pinConfigGpioLpc4337_t.PNG)

                    * Los tipos de datos de esa estrucutra son:

                    typedef struct{
                       int8_t port;
                       int8_t pin;
                    } pinConfigLpc4337_t;
------------------------------------------------------------------------
                    int8_t
------------------------------------------------------------------------
                    typedef struct{
                       int8_t port;
                       int8_t pin;
                    } gpioConfigLpc4337_t;
------------------------------------------------------------------------

     * Entro a Chip_GPIO_SetPinState

![](https://github.com/Hitalio/TP1/blob/master/images/Chip_GPIO_SetPinState.PNG)
            Donde el primer tipo de dato es una estructura que define la estructura de puertos
![](https://github.com/Hitalio/TP1/blob/master/images/LPC_GPIO_T.PNG)

# Punto 2:

# Punto 3:

# Punto 4:

# Punto 5:

# Punto 6:
