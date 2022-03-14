AT commands used to format the data nicely for logging, compatible with any ELM327 device.  You can find a good breakdown of all the ELM327 AT commands via [SparkFun's website](https://www.sparkfun.com/datasheets/Widgets/ELM327_AT_Commands.pdf).

# Initialization
```
ATH1     # Display Headers
ATL1     # Include line feeds
ATS1     # Spaces (just so it's easier to look at)
ATCAF0   # Disable CAN Automatic Formatting - This seems to strip some data from the packets so we turn it off
ATCM000  # Remove any Header filter masks
```

# Monitor All (`ATMA`)
You can go into monitor mode (basically dump all traffic to terminal) using `ATMA`, but keep in mind that most Bluetooth ELM327 devices will immediately fill their buffers and stop monitoring.  It's recommended to use a **USB-based** ELM327 device for broad traffic dumping.  Bluetooth is fine if you have a filter enabled.

# Filtering (`ATCF` and `ATCM`)
You can use `ATCFxxx` to set a Header filter (replacing `xxx` with the Header ID) in conjuntion with Monitor All to narrow down the amount of data fed back to you.  Once a filter is set, you can enable it with `ATCMFFF`.  The last three characters (FFF) set the mask in hex -- So you can set something like **F00** to catch all Headers starting with the same first character.