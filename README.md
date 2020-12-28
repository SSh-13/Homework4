Homework4
//
//  main.swift
//  Homework_4
//
//  Created by Sergey Sherstnikov on 28.12.2020.
//

import Foundation


enum boost{
    case boostOn
    case boostOff
}

enum trunkBody{
    case trunkIsFull
    case TrunkIsEmpty
}

class Car{
    var brand: String
    var release: Int
    init(brand: String, release: Int){
        self.brand = brand
        self.release = release
    }
}

class trunkCar: Car{
    var trunk: trunkBody
    init(brand: String, release: Int, trunk: trunkBody){
        self.trunk = trunk
        super.init(brand: brand, release: release)
    }
    
    func trunkState(){
        if trunk == .trunkIsFull {
            print("Багажник полон")
        } else{
            print("Багажник пуст")
        }
    }
}


class sportCar: Car{
    var goFast: boost
    init(brand: String, release: Int, goFast: boost){
        self.goFast = goFast
        super.init(brand: brand, release: release)
    }
    
    func boostState(){
        if goFast == .boostOn {
            print("Спортивная машина едет быстрее")
        } else{
            print("Спортивная машина едет медленее")
        }
    }
}


let kamaz = trunkCar(brand: "КАМАЗ", release: 2001, trunk: .trunkIsFull)
kamaz.trunkState()

let lamborghini = sportCar(brand: "lamborghini", release: 2019, goFast: .boostOn)
lamborghini.boostState()
