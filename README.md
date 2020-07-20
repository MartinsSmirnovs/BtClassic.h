# BtClassic.h
# Table of contents
- [Usage](https://github.com/Onii-Chaan/BtClassic.h/blob/master/README.md#usage)
- [Methods](https://github.com/Onii-Chaan/BtClassic.h/blob/master/README.md#methods)
- [Protocol](https://github.com/Onii-Chaan/BtClassic.h/blob/master/README.md#protocol)
- [Examples](https://github.com/Onii-Chaan/BtClassic.h/blob/master/README.md#examples)

# Usage

Arduino library for receiving Serial data on Rx/Tx pins and processing it. Using custom made protocol, you can send up to 10 commands and parameters with them.

# Methods

- ```BtClassic()``` initializes BtClassic object
- ```void checkNewData()``` gets new incoming data and assigns it to variables
- ```bool getNewData()``` returns true if new data has been received and processed
- ```void loop()``` main loop, must be placed in loop
- ```byte getType()``` gets type value (0 - 9) 
- ```int getValue()``` gets main value (0 - 999)

# Protocol 

Data has to be sent in specific way in order for this library to process it. The way data needs to be sent looks like this:
- ```<[yourType][yourValue]>```

- First must always come ```<``` sign and so must be ```>``` at the end
- ```yourType``` must be one digit number 
- ```yourValue``` must be three digit number

If you want to send ```yourValue`` that is less than 100 or 10, additional zeros must be added, like 099 or 009

# Examples

- ```<2411>```
type = 2
value = 411

- ```<0002>```
type = 0
value = 2

- ```<0000>```
type = 0
value = 0
