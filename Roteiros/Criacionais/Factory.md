
## O que é?
O Factory é um padrão...

## Exemplo
```python
class Car:
	def __init__(self, color, n_doors=2, max_velocity=120):
		self.color = color
		self.n_doors = n_doors
		self.max_velocity = max_velocity
		
class Bike:
	def __init__(self, color, max_velocity=120):
		self.color = color
		self.max_velocity = max_velocity

class VehicleFactory:
	_registry= {
		"car": Car,
		"bike": Bike
	}
	
	def __call__(self, obj, *args, **kwargs):
		return self._registry[obj](*args, **kwargs)


factory = VehicleFactory()
car = factory('car', 'red', 4, 150)
bike = factory('bike', 'red' 200)

print(car.max_velocity) # Output is: 150
print(bike.max_velocity) # Output is: 200
```