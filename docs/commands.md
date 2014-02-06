# Commands

## land()

Initiates a landing sequence.

##### Returns 

`nil`

## takeoff()

Initiates take off sequence.

##### Returns 

`nil`

## hover() 

Makes the crazyflie hover in a position.

##### Returns 

`nil`

## setPitch(deg)

Orders crazyflie to go forward or backward by the amount specified by deg.

##### Params

- **deg** - The degrees which to return data

##### Returns 

`nil`

## setYaw(deg) 

Orders crazyflie to turn left or right by the amount specified by deg.

##### Params

- **deg** - The degrees which to return data

##### Returns 

`nil`

## setThrust(accelerate) 

Orders crazyflie to accelerate.

##### Params

- **accelerate** - The acceleration which to return data

##### Returns 

`nil`

## shutdown() 

Shutdown the device.

##### Returns 

`nil`

## setParam(param, value)

Set the parameters for crazyflie.

##### Params

- **param** - params
- **value** - params

##### Returns 

`(param, value)`