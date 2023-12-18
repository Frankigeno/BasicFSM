# BasicFSM

BasicFSM is a Python library that aims to simplify Finite State Machine creation in Python. 
### Features

- The machine runs indipendently from the rest of the code
- It supports multiple machines per code
- Doesn't need third part libraries

### Installation

```sh
pip install basicfsm
```


### Example

Basic FSM structure
```python
from BasicFSM import FSMConstructor # import the library
from time import sleep

fsm = FSMConstructor()
# declaring internal fsm variables
fsm.variables["count1"] = 0
fsm.variables["count2"] = 0

def state1():
    fsm.variables["count1"] += 1
    print(fsm.variables["count1"])
    sleep(1)
    
def state2():
    fsm.variables["count2"] += 1
    print(fsm.variables["count2"])
    sleep(1)

# the function that will control the state switch
def state1_condition():
    if fsm.variables["count1"] >= 10:
        fsm.change_state("state2")

# declare all the states
fsm.define_states(state1, state2)
# start the fsm at the defined state
fsm.start("state1")
```
