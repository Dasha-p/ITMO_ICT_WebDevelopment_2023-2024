# Модель Ticket

Модель `Ticket` описывает билеты для различных полетов.

## Поля:

- **flight** - Ссылка на модель `Flight`. Указывает, к какому рейсу относится данный билет. Тип: ForeignKey.

- **seat_class** - Класс обслуживания для данного билета (например, эконом, комфорт, бизнес, первый класс). Тип: CharField с выбором из предопределенного списка.

- **seat** - Номер места на рейсе. Тип: CharField.

- **is_booked** - Индикатор, показывающий, забронирован ли билет. Тип: BooleanField. 

- **price** - Цена билета. Тип: DecimalField.
