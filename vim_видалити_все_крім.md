
#vim #vimg #delete

У режимі команд (Normal Mode) наберіть наступну команду:

```vim
:g!/sometext/d
```

vim

`:g/текст_який_залишаємо/ v/текст_який_хочемо_видалити/`

Де:

- `текст_який_залишаємо` - це текст, який має бути у рядках, які ви хочете залишити.
- `текст_який_хочемо_видалити` - це текст, який має бути у рядках, які ви хочете видалити.

Наприклад, якщо ви хочете залишити всі рядки, які містять слово "apple", і видалити решту рядків, команда виглядатиме так:

vim

1. `:g/apple/ v/./d`
    
    У цій команді `.` вказує на будь-який символ, тобто вона видалить усі рядки, які не містять слово "apple".
    
2. Натисніть клавішу `Enter`, і Vim видалить всі рядки, які не містять вказаний текст.
    

Будьте обережні при використанні цієї команди, оскільки вона безповоротно видалить рядки з вказаним текстом. Переконайтеся, що ви зрозуміли, як ця команда працює, і створіть резервну копію файлу перед використанням.