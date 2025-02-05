# Проект "Моя Жизнь"


## 📖 Описание

Добро пожаловать в проект моей жизни! Это мой путь к самореапизации, где я постоянно развиваюсь, учусь новому и достигаю поставленных целей. В этом файле описаны ключевые моменты моего образования, карьеры и личных интересов.

```bash
```

## 🌿 Личностные качества и навыки

• Креативное мышление - постояино нахожу нестандартные рещения для различных задач.
• Командная работа - умею эффективно взаимодействовать с коллегами для достижения общих целей.
• Организованность - соблюдаю сроки и умею управлять временем.
• Навыки переговоров - обладаю опытом проведения переговоров на разных уровнях. 
• Адаптивность - быстро реагирую на изменения в условиях работы и жизни.

```bash
```

## 📜 Цели

1. Овладеть новыми навыками в DE, чтобы расширить профессиональные возможности.
2. Принять участие DE, чтобы улучшить свои знания и наладить новые контакты.
3. Развить свои знания и области DE и достичь экспертизы.

## 🙌 Связаться со мной

Email: MaksSokol@rabora.ru
Телефон: +023 673 2893

## 💭 Заключение

Этот "README" - это мой жизненный план, который развивается каждый день.




Итоговое задание по Python:

purchases = [
    {"item": "apple", "category": "fruit", "price": 1.2, "quantity": 10},
    {"item": "banana", "category": "fruit", "price": 0.5, "quantity": 5},
    {"item": "milk", "category": "dairy", "price": 1.5, "quantity": 2},
    {"item": "bread", "category": "bakery", "price": 2.0, "quantity": 3},

]


def total_revenue(purchases: list)->int:
    return sum(map(lambda x: x['price'] * x['quantity'], purchases))


def items_by_category(purchases: list)->dict:
    res = dict()
    for d in purchases:
        res[d['category']] = res.get(d['category'],set())
        res[d['category']].add(d['item'])
    return res


def expensive_purchases(purchases:list, min_price:float):
    return [d for d in purchases if d['price'] >= min_price]


def average_price_by_category(purchases:list)->dict:
    res = dict()
    for d in purchases:
        res[d['category']] = res.get(d['category'], [])
        res[d['category']].append(d['price'])
    return {k : (sum(v)/len(v)) for k,v in res.items()}


def most_frequent_category(purchases:list)->str:
    res = dict()
    for d in purchases:
        res[d['category']] = res.get(d['category'], [])
        res[d['category']].append(d['quantity'])
    res = {k: sum(v) for k, v in res.items()}
    return max(res, key=res.get)

print(f'Общая выручка: {total_revenue(purchases)}')
print(f'Товары по категориям: {items_by_category(purchases)}')
print(f'Покупки дороже 1.0: {expensive_purchases(purchases, 1)}')
print(f'Средняя цена по категориям: {average_price_by_category(purchases)}')
print(f'Категория с наибольшим количеством проданных товаров: {most_frequent_category(purchases)}')