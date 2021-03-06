# TPGApi
TPG API wrapper to fetch stops and next departures for Geneva's public transport.

## Installation
### Using Cocoapods

Add this line in your PodFile

```
pod 'TPGApi'
```


## Usage

To use the API you must have a valid API key, you can request one here http://www.tpg.ch/web/open-data/donnees-tpg

You have to provide wherever you want in the code like this:

```
TPGApiKey.key = "your key"
```

### List of all stops in Geneva

Stops have to be loaded at least once, this is done asychronously. Once downloaded the stops are cached on the device.
```
StopManager.instance.loadStops(completion: {(commercialStops, physicalStops) in

}, force: false)
```

### Next departures for a stop

Get next departures for stop code 'Gare Cornavin'
```
DeparturesManager.instance.loadNextDeparturesFor(stopCode: "CVIN", completion: {departures in

})
```

### Steps for a given departure

Get the steps for the line of the departure '43844'
```
DeparturesManager.instance.loadThermometerFor(departureCode: "43844", completion: {steps in

})
        
```
