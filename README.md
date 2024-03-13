```
// Описание структур

// Структура для легкового автомобиля
struct Car {
    let brand: String
    let year: Int
    var trunkVolume: Double
    var engineRunning: Bool
    var windowsOpen: Bool
    var filledTrunkVolume: Double
    
    mutating func performAction(action: CarAction) {
        switch action {
        case .startEngine:
            engineRunning = true
        case .stopEngine:
            engineRunning = false
        case .openWindows:
            windowsOpen = true
        case .closeWindows:
            windowsOpen = false
        case .loadCargo(let volume):
            filledTrunkVolume += volume
        case .unloadCargo(let volume):
            filledTrunkVolume -= volume
            if filledTrunkVolume < 0 {
                filledTrunkVolume = 0
            }
        }
    }
}

// Структура для грузовика
struct Truck {
    let brand: String
    let year: Int
    var cargoVolume: Double
    var engineRunning: Bool
    var windowsOpen: Bool
    var filledCargoVolume: Double
    
    mutating func performAction(action: TruckAction) {
        switch action {
        case .startEngine:
            engineRunning = true
        case .stopEngine:
            engineRunning = false
        case .openWindows:
            windowsOpen = true
        case .closeWindows:
            windowsOpen = false
        case .loadCargo(let volume):
            filledCargoVolume += volume
        case .unloadCargo(let volume):
            filledCargoVolume -= volume
            if filledCargoVolume < 0 {
                filledCargoVolume = 0
            }
        }
    }
}

// Перечисление с возможными действиями с автомобилем
enum CarAction {
    case startEngine
    case stopEngine
    case openWindows
    case closeWindows
    case loadCargo(volume: Double)
    case unloadCargo(volume: Double)
}

// Перечисление с возможными действиями с грузовиком
enum TruckAction {
    case startEngine
    case stopEngine
    case openWindows
    case closeWindows
    case loadCargo(volume: Double)
    case unloadCargo(volume: Double)
}

// Создание экземпляров структур
var myCar = Car(brand: "Toyota", year: 2020, trunkVolume: 500, engineRunning: false, windowsOpen: false, filledTrunkVolume: 0)
var myTruck = Truck(brand: "Volvo", year: 2018, cargoVolume: 2000, engineRunning: false, windowsOpen: false, filledCargoVolume: 0)

// Применение действий к автомобилю и грузовику
myCar.performAction(action: .startEngine)
myCar.performAction(action: .openWindows)
myCar.performAction(action: .loadCargo(volume: 100))
myTruck.performAction(action: .startEngine)
myTruck.performAction(action: .loadCargo(volume: 500))

// Положить объекты структур в словарь как ключи
var vehiclesDict: [String: Any] = [:]
vehiclesDict["myCar"] = myCar
vehiclesDict["myTruck"] = myTruck

```
![изображение](https://github.com/vihuhool/swifty6/assets/69204363/4509e010-29e8-475a-97b9-c4ae29ad66a4)
