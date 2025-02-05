# CustomUser

`CustomUser` является расширенной моделью пользователя Django, наследующей `AbstractUser`. Эта модель содержит как стандартные поля (например, имя пользователя, пароль), так и дополнительные поля.

## Поля:

- **email**  
  Тип: EmailField  
  Описание: Адрес электронной почты пользователя.


- **phone_number**  
  Тип: CharField (макс. длина 11 символов)  
  Описание: Номер телефона пользователя.


- **first_name**  
  Тип: CharField (макс. длина 30 символов)  
  Описание: Имя пользователя.


- **last_name**  
  Тип: CharField (макс. длина 30 символов)  
  Описание: Фамилия пользователя.


- **middle_name**  
  Тип: CharField (макс. длина 30 символов)  
  Описание: Отчество пользователя.


- **citizenship**  
  Тип: CharField (макс. длина 100 символов)  
  Описание: Гражданство пользователя.


- **date_of_birth**  
  Тип: DateField  
  Описание: Дата рождения пользователя.


- **gender**  
  Тип: CharField (макс. длина 1 символ)  
  Описание: Пол пользователя. Может принимать значения: `M` (Мужской) или `F` (Женский).
