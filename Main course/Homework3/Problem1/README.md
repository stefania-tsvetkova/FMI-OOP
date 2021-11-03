# Problem 1

Съществуват различни видове броячи - някои могат само да увеличават бройката, която пазят, други могат и да я намалят, а трети имат ограничение до колко могат да отброяват.

### Клас `Counter`

Най-простият брояч - само нагоре, без ограничение.

*	Конструктор без параметри: началната стойност е 0 и стъпката на брояча е 1
*	Конструктор с 1 параметър int initial: началната стойност е initial, а стъпката е 1
*	Конструктор с 2 параметъра int initial, unsigned step: началната стойност е initial, а стъпката e step
*	increment(): увеличава текущата стойност със стъпката на брояча
*	getTotal(): връща int - текущата отброена стойност
*	getStep(): връща unsigned - стъпката на брояча (не трябва да може да бъде променяна)

### Клас `TwowayCounter`

Брояч, който може и да намалява отброяваната стойност.

Освен всичко изброено в Counter, съдържа и:
*	decrement(): намалява текущата стойност със стъпката на брояча

### Клас `LimitedCounter`

Брояч, който отброява само до дадена максимална стойност.

*	Конструктор с 1 параметър int max: максималната стойност е max, началната е 0, а стъпката е 1
*	Конструктор с 2 параметъра int max, int initial: максималната стойност е max, началната е initial, а стъпката е 1
*	Конструктор с 3 параметъра int max, int initial, unsigned step: максималната стойност е max, началната е initial, а стъпката е step
*	increment(): увеличава текущата стойност със стъпката на брояча само ако няма да надмине максималната
*	getMax(): връща int - максималната стойност на брояча
*	getTotal(): същия като този на Counter
*	getStep(): същия като този на Counter

### Клас `LimitedTwowayCounter`

Той е и LimitedCounter и TwowayCounter едновременно: може да отброява нагоре до определена максимална стойност и надолу до определена минимална стойност.

*	Конструктор с 2 параметъра int min, int max: минималната стойност е min, максималната стойност е max, началната е 0, а стъпката е 1
*	Конструктор с 3 параметъра int min, int max, int initial: минималната стойност е min, максималната стойност е max, началната е initial, а стъпката е 1
*	Конструктор с 4 параметъра int min, int max, int initial, unsigned step: минималната стойност е min, максималната стойност е max, началната е initial, а стъпката е step
*	increment(): същия като на LimitedCounter
*	decrement(): намаля текущата стойност със стъпката на брояча само ако няма да стане по-ниска от минималната
*	getMin(): връща минималната стойност на брояча
*	getMax(): същия като този на LimitedCounter
*	getTotal(): същия като този на Counter
*	getStep(): същия като този на Counter

### Клас `Semaphore`

Най-простия бинарен семафор - това е LimitedTwowayCounter, който има минимална стойност 0, максимална стойност 1 и стъпка 1. Използва се от процесите в операционнитe системи за синхронизационни цели. (Повече информация - след 1 година в курса по ОС)

* Конструктор без параметри - началната стойност на брояча е 0.
*	Конструктор с един параметър bool - при true началната стойност на брояча е 1, а при false е 0.
*	isAvailable(): връща bool, показващ дали стойността на брояча е над 0
*	wait() - прави същото като decrement() на LimitedTwowayCounter
*	signal() - прави същото като increment() на LimitedTwowayCounter