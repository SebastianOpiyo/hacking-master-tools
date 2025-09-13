 # Bluetooth Low Energy (BLE) Notes
 
        +-------------------------------------------------+
        |              Applications                       |
        +---------------------------------------+---------+
        |        Generic Attribute Profile      | Generic |
        +--------------------+------------------+ Access  |
        | Attribute Protocol | Security Manager | Profile |
        +--------------------+------------------+---------+
        |  Logical Link Control and Adaptation Protocol   |
   - - -+-----------------------+-------------------------+- - - HCI
        |      Link Layer       |    Direct Test Mode     |
        +-------------------------------------------------+
        |             Physical Layer                      |
        +-------------------------------------------------+

                   Figure 1: Bluetooth LE Protocol Stack


## BLE protocol Stack Layers Simple explanation:

    *Physical Layer*: Sends bits over the air.

    *Link Layer*: Manages device connections and timing.

    *L2CAP*: Formats data packets.

    *Security Manager*: Keeps connection secure.

    *ATT & GATT*: Share meaningful data between devices.

    *GAP*: Controls connection initiation and discovery.

    *Applications*: Use Bluetooth for useful purposes.
