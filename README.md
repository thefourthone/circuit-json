Circuit JSON
============

Abstract
--------
A simple specification for a circuit diagram file type. As suggested by the name the specification relies on JSON encoding as the main data carrier. 

Examples
--------
```json
{
  "0":{
    "part":"battery",
    "pos":[0,0],
    "wires":[
      [0,1,4],
      [1,1,5],
      [0,2,0],
      [0,2,2]
    ]
  },
  "1":{
    "part":"attiny85",
    "pos":[0.25,0],
    "wires":[
      [0,2,1]
    ]
  },
  "2":{
    "part":"slider",
    "pos":[0.5,0],
    "wires":[
      []
    ]
  },
  "attiny85":{
    "height":0.5,
    "width":0.25,
    "pinout":[
      [],
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
The data can be separated into to main types: object types and layout. 


