# Seeed ArduPy P9813 [![Build Status](https://api.travis-ci.com/Seeed-Studio/seeed-ardupy-tm1637.svg?branch=master)](https://travis-ci.com/github/Seeed-Studio/seeed-ardupy-tm1637)

## Introduction

4 digit display module is usually a 12 pin module. In this Grove gadget, we utilize a TM1637 to scale down the controlling pins into 2 Grove pins. It only takes 2 digital pins of Arduino or Seeeduino to control the content, even the luminance of this display. For projects that require of alpha-numeric display, this can be a nice choice.

You can get more information in here [Grove_4Digital_Display](https://github.com/Seeed-Studio/Grove_4Digital_Display).


![Grove_4Digital_Display](https://statics3.seeedstudio.com/images/product/4-Digital%20Display.jpg)


## How to binding with ArduPy
- Install [AIP](https://github.com/Seeed-Studio/ardupy-aip)
- Build firmware with Seeed ArduPy TM1637
```
    aip install Seeed-Studio/seeed-ardupy-tm1637
    aip build
```
- Flash new firmware to you ArduPy board
```
    aip flash # + Ardupy Bin PATH
```
For more examples of using AIP, please refer to [AIP](https://github.com/Seeed-Studio/ardupy-aip).

## Usage

```
from arduino import grove_4_digital_display
import time

nixie_tube = grove_4_digital_display(0, 1)
nixie_tube.show_colon = True

while True:
    for s in range(60, -1, -1):
        for ss in range(59, -1, -1):
            value = s * 100 + ss
            nixie_tube.display(value)
            time.sleep(0.01)
        nixie_tube.show_colon = not nixie_tube.show_colon 
```

## API Reference

- **clear()**

    Clear display
    ```
    nixie_tube.clear() 
    ```

- **display(*number\<int\>*)**
    
    Display number
    ```
    nixie_tube.display(1234) # display 1234
    ```
- **show_colon** 
    Control colon
    ```
    nixie_tube.show_colon = True # make colon light on
    ```

----

This software is written by seeed studio<br>
and is licensed under [The MIT License](http://opensource.org/licenses/mit-license.php). Check License.txt for more information.<br>

Contributing to this software is warmly welcomed. You can do this basically by<br>
[forking](https://help.github.com/articles/fork-a-repo), committing modifications and then [pulling requests](https://help.github.com/articles/using-pull-requests) (follow the links above<br>
for operating guide). Adding change log and your contact into file header is encouraged.<br>
Thanks for your contribution.

Seeed Studio is an open hardware facilitation company based in Shenzhen, China. <br>
Benefiting from local manufacture power and convenient global logistic system, <br>
we integrate resources to serve new era of innovation. Seeed also works with <br>
global distributors and partners to push open hardware movement.<br>