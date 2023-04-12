
## O que é?
O Factory é um padrão...

## Exemplo
```python
class Car:
	def __init__(self, color, n_doors=2, max_velocity=120):
		self.color = color
		self.n_doors = n_doors
		self.max_velocity = max_velocity
class SportCar(Car):
	def __init__(self, *args, **kwargs):
		super(*args, **kwargs)
		self.type = "Sport"
class ConversibleCar(Car):
	def __init__(self, *args, **kwargs):
		super(*args, **kwargs)
		self.type = "Conversible"

class CarFactory:
	_registry = {
		"Conversible": ConversibleCar,
		"Sport": SportCar
	}
	def new(self, car_type, *args, **kwargs):
		return self._registry[car_type](*args, **kwargs)

car_factory = CarFactory()
convertible = car_factory.new("Conversible", "gray", n_doors = 4)
sport = car_factory.new("Sport", "red", max_velocity = 250)

print(convertible.type) # Output is: "Conversible"
print(sport.type) # Output is: "Sport"
```