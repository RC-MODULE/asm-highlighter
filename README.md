# Подсветка синтаксиса языка ассемблера NeuroMatrix
___

Реализация подсветки синтаксиса ассемблера NeuroMatrix для [Notepad++](https://notepad-plus-plus.org/) и [Microsoft Visual Studio](https://www.visualstudio.com/) 2013 (кроме Express) и 2015.

## Notepad++ 

Notepad++ — свободный текстовый редактор с открытым исходным кодом для Windows с подсветкой синтаксиса большого количества языков программирования и разметки.

Поддерживаемые опции:
* Подсветка синтаксиса;
* Сворачивание комментариев;
* Автодополнение кода. 

### Установка в Notepad++  
[Главное меню->Синтаксисы->Задать свой синтаксис]  
[Импортир..] ... выбрать NeuroMatrix-Notepad-UDL.xml  
[Польз. язык]  ... выбрать "NeuroMartix Assembly"  
[Сохранить как...] ... [Name: ]  ввести NeuroMatrix ASM  

В меню [Главное меню->Синтаксисы] должен появиться пункт "NeuroMatrix ASM"  

Если подсветка при открытии .asm не включается автоматически необходимо обновить версию Notepad++, либо выбрать  "NeuroMatrix ASM" вручную.

### Пример работы

![Notepad++](/Notepad++/Screenshot.PNG?raw=true)

### Настройка вида "Список функций" в Notepad++ для ассемблерных файлов
Удобную навигацию по меткам ассемлерного файла можно сделать сделующим образом:

1. открываем файл 
%AppData%\Notepad++\functionList.xml

2. добавляем  перед тегом ```</associationMap>```   

```<association id="neuromatrix_label"  userDefinedLangName="NeuroMatrix ASM"/>```  
	  

3. добавляем  перед тегом  ```</parsers>```   
```css
<!-- ======================================================= [ NeuroMatrix ] -->
<parser id="neuromatrix_label" displayName="NeuroMatrix" commentExpr="((/\*.*?\*))">
	<function
		mainExpr="(^[\t ]*<[\w]+>)|(^[\t ]*[\w]+:)" 
		displayMode="$functionName">
		<functionName>
			<nameExpr expr="\w*"/>
		</functionName>
	</function>
</parser>
```
4. Перегружаем Notepad++			
5. Включаем отображение списка функций	Меню->Вид->Список функций. 
![Notepad++](/Notepad++/FunctionList.png?raw=true)

>Для работы FunctionList необходим установленный синтаксис языка "NeuroMatrix ASM"

пример готового [functionList.xml](/Notepad++/functionList.xml)



## Visual Studio

Microsoft Visual Studio — интегрированная среда разработки программ, позволяющая при использовании makefile разрабатывать программы для Neuromatrix на языках C/C++ и языке ассемблера. 

Поддерживаемые опции:
* Подсветка синтаксиса;
* Сворачивание комментариев;
* Автодополнение кода;
* IntelliSense (информация о вводимой команде).

### Установка в Visual Studio

Средство поддержки языка ассемблера распространяется в виде расширения Visual Studio в формате VSIX. Для возможности получения обновлений через интернет плагин был размёщён по следующему адресу: [NeuroMatrix assembly language](https://visualstudiogallery.msdn.microsoft.com/ca93d385-b301-4f64-85e9-fa924d8304ab).

Для скачивания плагина не требуется регистрация, скачанный плагин автоматически определяет подходящие версии Visual Studio для установки. 

### Пример работы

![Light theme](/Visual Studio/Light_web.PNG?raw=true)

![Dark theme](/Visual Studio/Dark_web.PNG?raw=true)


