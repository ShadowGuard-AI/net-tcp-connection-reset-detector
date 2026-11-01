# net-tcp-connection-reset-detector
Monitors TCP connections and detects abnormal connection resets (RST packets), indicating potential network issues or malicious activity. Filters connections based on IP addresses and port numbers. - Focused on Basic network operations

## Install
`git clone https://github.com/ShadowStrikeHQ/net-tcp-connection-reset-detector`

Install the requirements with `pip install -r requirements.txt`. The tool uses only the Python standard library, so there is nothing third party to install.

## Usage
`python3 main.py [params]`

Example: `python3 main.py -i eth0 --promiscuous --log_file rst_detector.log --verbose`

## Parameters
- `-h, --help`: Show help message and exit
- `--interface, -i`: Network interface to listen on (e.g., eth0, wlan0). Defaults to eth0.
- `--src_ip`: Filter by source IP address (optional).
- `--dst_ip`: Filter by destination IP address (optional).
- `--src_port`: Filter by source port (optional).
- `--dst_port`: Filter by destination port (optional).
- `--promiscuous`: Enable promiscuous mode (requires root). On Linux this is set on the packet socket with PACKET_ADD_MEMBERSHIP for the named interface.
- `--log_file`: Path to log file (optional).
- `--verbose`: Enable verbose logging. Sets the log level to DEBUG and, for each detected RST packet, logs the packet headers and the payload length only. Packet payload contents are never printed or written to the log file.

## License
Copyright (c) ShadowStrikeHQ
