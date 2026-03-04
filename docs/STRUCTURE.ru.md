# Arma 3 Community Config Standard 0.0.1 (A3CCS)
## [English](STRUCTURE.md) | Русский

## Структура

### 1. Общие правила:
  1. Каждый класс начинается с ключевого слова class, за которым следует имя класса и при необходимости наследование:
  ```
  class My_Class : Parent_Class
  ```
  2. Фигурные скобки {} всегда открываются на той же строке, закрываются на отдельной строке:
  ```
  class My_Class {
  ...
  }
  ```
  3. Отступы — 4 пробела на уровень вложенности.
  4. Между логическими секциями допускается одна пустая строка.
  5. Вложенные маленькие классы (≤3 свойства) можно писать без пустых строк внутри.

### 2. Порядок логических секций в классе
Рекомендуемый порядок логических секций внутри класса:
  1. Основные свойства: `scope, author, displayName, side`
  2. Модель и визуальные элементы: `model, picture, hiddenSelectionsTextures`
  3. Экипировка и оружие: `weapons[], magazines[], linkedItems[]`
  4. EventHandlers: `init, fired, killed`

При этом сам порядок значений внутри секции значения не имеет и выбирается автором по его личному желанию (например, можно сначала поставить `displayName`, а потом `scope`, и наоборот). Главное, чтобы порядок самих секций в классе соблюдался.

Например:
  ```
  class My_Soldier : B_Soldier_F
  {
      scope = 2;
      displayName = "My Soldier";
      model = "\myMod\units\mysoldier.p3d";
      picture = "\myMod\data\ui\icon_ca.paa";
      weapons[] = {"arifle_MX_F"};
      magazines[] = {"30Rnd_65x39_caseless_mag"};
      linkedItems[] = {};
      class EventHandlers
      {
          init = "_this call my_fnc_init;";
      };
  };
  ```
