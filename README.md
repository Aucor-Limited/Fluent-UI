# Fluent UI documentation
# Обзор
Библиотека UI разработана, чтобы помочь вам создать простой, но настраиваемый GUI в Roblox. Эта документация охватывает доступные функции и то, как их эффективно использовать.
# Начиная
Чтобы загрузить библиотеку пользовательского интерфейса в игру Roblox, используйте следующий код:
```lua
local uiLibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/RScripter/Fluent-UI-library/main/Source/Source.lua"))()
```
# Создать окно

Описание:
Создает новое окно с заголовком и двумя фреймами: один для вкладок, другой для основного содержимого.

Пример использования:
```lua
local window = uiLibrary:MakeWindow({Name = "My Window"})
```
# Создать вкладку

Описание:
Добавляет новую вкладку в фрейм вкладок. Вкладка отобразит свое содержимое в главном фрейме при щелчке.

Пример использования:
```lua
uiLibrary:addTab({Name = "Tab 1"})
```
# Создать кнопку

Описание:
Добавляет кнопку к содержимому указанной вкладки.

Пример использования:
```lua
uiLibrary:addButton({
    TabName = "Tab 1",
    Name = "Click Me",
    Function = function()
        print("Button clicked!")
    end
})
```
# Создать переключатель

Описание:
Добавляет переключатель к содержимому указанной вкладки.

Пример использования:
```lua
local Toggle = Tabs.Main:CreateToggle("MyToggle", {Title = "Toggle", Default = false })

Toggle:OnChanged(function()
    print("Toggle changed:", Options.MyToggle.Value)
end)
```

# Создать слайдер

Описание:
Добавляет слайдер к содержимому указанной вкладки.

Пример использования:
```lua
local Slider = Tabs.Main:CreateSlider("Slider", {
    Title = "Slider",
    Description = "This is a slider",
    Default = 2,
    Min = 0,
    Max = 5,
    Rounding = 1,
    Callback = function(Value)
        print("Slider was changed:", Value)
    end
})
```
```lua
Slider:OnChanged(function(Value)
    print("Slider changed:", Value)
end)
```
```lua
Slider:SetValue(3)
```
# Создать выпадающие меню
Описание:
Добавляет выпадающие меню к содержимому указанной вкладки.

Пример использования:
```lua
local Dropdown = Tabs.Main:CreateDropdown("Dropdown", {
    Title = "Dropdown",
    Values = {"one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten", "eleven", "twelve", "thirteen", "fourteen"},
    Multi = false,
    Default = 1,
})
```


# Примечания
- Убедитесь, что вкладки добавлены, прежде чем добавлять к ним кнопки или надписи.
- `uiLibrary` автоматически управляет видимостью вкладок и их содержимым в зависимости от взаимодействия с пользователем.
- `Размер рамок` прокрутки автоматически настраивается по мере добавления новых элементов пользовательского интерфейса.
