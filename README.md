# PowerdByIllia
Software Switch

## How to run:
```bash
python3 app or python app
```
>if you run it on linux, you need to run it as root

First, you need to boot the switch, after add interface you want to sniffer:
```
boot
input interface: lo
```
Run sniffer:
```
run
```
If you want to stop sniffer:
```
stop
```
If you want to stop switch:
```
shutdown or exit
```
Help:
```
help
```

### To create python classes based on yang models:

First, install virtualenv:
```bash
pip install virtualenv
```

Then, run it:
```bash
source env/bin/activate
```
Install pyangbind and pyang:
```bash
pip install pyang pyangbind
```

To create python classes based on yang models, run:
```bash
export PYBINDPLUGIN=`path/to/project/env/bin/python -c \
> 'import pyangbind; import os; print ("{}/plugin".format(os.path.dirname(pyangbind.__file__)))'`
```
- mac:
```bash
pyang -p templates/yang_models/ --plugindir $PYBINDPLUGIN -f pybind -o templates/yang_py/sw_mac_table.py templates/yang_models/mac-table.yang
```
- interface:
```bash
pyang --plugindir $PYBINDPLUGIN -f pybind -o templates/yang_py/sw_interface.py templates/yang_models/interface.yang
```


