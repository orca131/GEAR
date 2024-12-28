---
aliases: 
date: 2023-12-01
tags: 
share: true
---
## Time-converter

```meta-bind
INPUT[number(defaultValue(420)):sec]
```

```meta-bind-js-view
{sec} as Sec
---
let showSignal = context.bound.Sec * 60;
let formattedTime = new Date(context.bound.Sec * 1000).toISOString().substring(14, 19);
let resultView = 'Время: ' + formattedTime + '\n' + 'Сигнал: ' + showSignal;
return engine.markdown.create(resultView);
```

```meta-bind
INPUT[progressBar(defaultValue(60),minValue(0), maxValue(833)):sec]
```

## fuel

| time  | steel | fuel type                                                        |
| ----- | :---: | ---------------------------------------------------------------- |
| 00:44 |  05   | ![coal](https://wiki.factorio.com/images/Coal.png)               |
| 02:13 |  16   | ![solid fuel](https://wiki.factorio.com/images/Solid_fuel.png)   |
| 08:40 |  62   | ![rocket fuel](https://wiki.factorio.com/images/Rocket_fuel.png) |

Печь запасает 5-6 единиц горючего.

```bash
13 = 11%
31 = 11%
17 = 22%
03 = 33%
07 = 44%
43 = 44%
02 = 55%
11 = 55%
29 = 55%
47 = 55%
19 = 77%
37 = 77%
05 = 88%
23 = 88%
41 = 88%
```

- `09 = 99%`
- `22 = 11%`

## timer-blueprint

- Постоянный комбинатор подаёт два сигнала (◻️,◼️) на вход арифметического комбинатора.
- Арифметический комбинатор ищет целочисленный остаток от деления значения белого сигнала (◻️) на значение чёрного (◼️) и присваивает белому сигналу (◻️) значение найденного остатка.
- В противном случае значение белого сигнала (◻️) увеличивается на 1 с каждым тиком сервера.

```blueprint
0eNqdU01vgzAM/S+WdqNVgX6N+w477DL1NlUoBHe1BgkKpluF+O9zoKKdpkl0l0iJ/Z7t95wWsqLBypFhSFrIsdaOKiZrIIHd88vTKwRA2poakrcWano3qvCZfK5QUk7kuJGXAIwq/cOQMdtBJziT4xckYbcPAA0TEw40/eWcmqbM0EnCiFaO+Fgik55pW2ZkFFsn5JWtaWiqBWGcLePH+SqAMyRxFEklaZCdLdIMj+pEApG8K1cq4bzH1z5wIFdzOnmUzyMx+nFq9DzTgVmh9IcH2gqdumj6IGm24aq5v4NuGNSgHkcJ/eEwv1WV8l5RTU43xP1VJPoRjrq9cEXTwGKfL/3LtWhs068HK8PTPYvnqz9cO1DB6O7cttEibRu/yOHN7gV38IyOXXjWi8XiShX2qv3PgUFE+QfSaCkFr78ugEJlWNx8t5PM3+sWbcPl5jHabLbxNo7XXfcNWag9xA==
```

___
- [Фёдор Ляпин: Комбинаторы](https://youtu.be/yVYTtkYN81E)
- [Time format mm:ss](../../javascript/2-digit-format.md)
- [Timer-first-prototype](../../obsidian/Meta-bind.md)
