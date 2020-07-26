# HomeKit Enviro+
An [Apple HomeKit](https://developer.apple.com/homekit/) accessory for the [Pimoroni Enviro+](https://shop.pimoroni.com/products/enviro?variant=31155658457171) running on a Raspberry Pi.

## Dependencies

* [**Go**](http://golang.org/doc/install) - this accessory is written in Go
* [**HomeControl**](https://github.com/brutella/hc) - to expose climate readings from the Enviro+ as an Apple HomeKit accessory
* [**enviroplus-exporter**](https://github.com/sighmon/enviroplus_exporter) - to read the sensors of the Enviro+ and export them for scraping by [Prometheus](https://prometheus.io)

## Installation

### Setup

1. Install [Go](http://golang.org/doc/install)
1. Clone this project: `git clone https://github.com/sighmon/homekit-enviroplus` and then `cd homekit-enviroplus`
1. Install the Go dependencies: `go get`
1. Install and run the Python [enviroplus-exporter](https://github.com/sighmon/enviroplus_exporter)
1. Optionally if you'd prefer a Docker container of the exporter, see: [balena-enviro-plus](https://github.com/sighmon/balena-enviro-plus)

### Build

1. To build this accessory: `go build homekit-enviroplus.go`

### Run

1. Execute the executable: `./homekit-enviroplus`
1. Or run with the command: `go run homekit-enviroplus.go`

## Reset this accessory

If you uninstall this accessory from your Apple Home, you'll also need to delete the stored data for it to be able to be re-added.

### macOS

1. Delete the data in the folder created: `homekit-enviroplus/Enviro+/`
1. Restart the executable

### Raspberry Pi

1. Remove the persistent data: `rm -rf /var/lib/homekit-enviroplus/data`
1. Restart the Raspberry Pi

## Thanks

This project uses the amazing work of [Matthias](https://github.com/brutella). Please consider donating if you found this useful.
