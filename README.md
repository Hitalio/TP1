# Documentación sobre el TP1

## Punto 1: Uso del IDE	

Inicialmente se siguieron los pasos de la guia del TP1 para instalar todo lo necesario para su realización.

Para la ejecución de cada programa se realiza la siguiente secuencia de pasos a seguir:

- Click derecho sobre el proyecto (firmware_v2) 
	- Clean Project
	- Build Project

![](https://github.com/Hitalio/TP1/blob/master/images/clean_build.PNG)

- Click en Debug

Si se modifica el archivo o se quiere ejecutar otro programa se tiene que abandonar el Debug:

![](https://github.com/Hitalio/TP1/blob/master/images/debug_terminate.PNG)

Luego se copio la carpeta sapi_examples/edu-ciaa-nxp/bare_metal/gpio/gpio_02_blinky a projects/TP1, la cuál corresponde con este repositorio de github. 




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


## Punto 2: Switch Leds

![](https://github.com/Hitalio/TP1/blob/master/images/main_switch_leds1.png)

 Se comienza por configurar la placa EDU-CIA-NXP

	* boardconfig() inicializa el hardware de la placa, inicilaiza el conteo de Ticks con tickInit() y configura los pines de entrada y salida para teclas
	* gpioconfig es una estructura de tipo pinConfigLpc4337_t, que fue mencionada en el punto 1, recibe dos datos GPIO0 (gpioMap_t) y GPIO_INPUT (gpioConfig_t).
	* valor es un tipo booleano que almacena el valor de la tecla leido.

![](https://github.com/Hitalio/TP1/blob/master/images/main_switch_leds2.png)

	*valor lee si el pulsador es presionado y guarda el valor 0 o 1.

![](https://github.com/Hitalio/TP1/blob/master/images/gpioRead.png)

		*gpioRead() recibe el pulsador que fue presionado, el cual esta definido en gpioMap_t y devuelve una variable booleana ret_val dependiendo de si fue presionado el pulsador o no.
		*gpioObtainPinConfig() fue analizada en el punto 1.

	*gpioWrite() recibe el LED que se desea prender, el cual esta definido en gpioMap_t, y el valor booleano de si fue presionado el pulsador. Fue analizada en el punto 1.

	Se repite el proceso para los distintos pulsadores y LEDS.

## Punto 3:

## Punto 4:

## Punto 5:

## Punto 6:
