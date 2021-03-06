Circuit JSON
============

Abstract
--------
A simple specification for a circuit diagram file type. As suggested by the name the specification relies on JSON encoding as the main data carrier. 

Examples
--------
```javascript
{
  "0":{
    "part":"battery",
    "pos":[0,0],
    "wires":[
      [0,1,4], //give power to the attiny85
      [1,1,5], //give ground to the attiny85
      [0,2,0], //power for slider
      [1,2,2]  //ground for slider
    ]
  },
  "1":{
    "part":"attiny85",
    "pos":[0.25,0],
    "wires":[
      [0,2,1] //signal cable from slider
    ]
  },
  "2":{
    "part":"slider",
    "pos":[0.5,0],
    "wires":[] //all wires are already accounted for
  },
  "attiny85":{
    "height":0.5,
    "width":0.25,
    "pinout":[
      [],  //leaving a blank pin to make pin numbering match the datasheet
      [0,0],
      [0,0.16],
      [0,0.33],
      [0,0.5],
      [0.25,0.5],
      [0.25,0.33],
      [0.25,0.16],
      [0.25,0]
    ]
  },
  "battery":{
    "height":0.5,
    "width":0.25,
    "pinout":[
      [0.25,0.1],
      [0.25,0.4],
    ]
  },
  "slider":{
    "height":0.5,
    "width":0.5,
    "pinout":[
      [0.1,0.1],
      [0.3,0.1],
      [0.4,0.1],
    ]
  }
}
```

Structure
---------
The data can be separated into to main types: object types and layout. Object types correspond to parts used in the circuit whereas layout describes how the parts are placed and how they are wired.

###Object Types

Object types are objects with `height`, `width` and `pinout` values. They are stored in the main object such that their index is a non-mumerical string.

`pinout` is an array of pin locations. Pin locations are arrays of length 2. The first element is the x cordinate in reference to the top left corner of the part; the second is the y component.

###Layout

Layout is defined by successive numerical string indices containing `part`, `pos` and `wire` values.

`wire` is defined as an array of wire objects.
a wire object is an array containing 3 values: pin on the originating part, index of other part, and pin on the other part. 




