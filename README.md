# Подсветка синтаксиса языка ассемблера NeuroMatrix и навигациия по меткам
___

Реализация подсветки синтаксиса ассемблера NeuroMatrix для [Notepad++](https://notepad-plus-plus.org/) и [Microsoft Visual Studio](https://www.visualstudio.com/) 2013 (кроме Express) и 2015.

## Notepad++ 

Notepad++ — свободный текстовый редактор с открытым исходным кодом для Windows с подсветкой синтаксиса большого количества языков программирования и разметки.

Поддерживаемые опции:
* Подсветка синтаксиса;
* Сворачивание комментариев;
* Автодополнение кода. 

### Установка синтакиса "NeuroMatrix ASM"	 в Notepad++  
[Главное меню->Синтаксисы->Задать свой синтаксис]  
[Импортир..] ... выбрать .\asm-highlighter\Notepad++\NeuroMatrix-Notepad-UDL.xml  
Закрыть, перегрузить Notepad

В меню [Главное меню->Синтаксисы] должен появиться пункт "NeuroMatrix ASM"  

Если подсветка при открытии .s или .asm не включается автоматически необходимо обновить версию Notepad++, либо выбрать синтакисис "NeuroMatrix ASM" вручную.

### Пример работы

![Notepad++](/Notepad++/Screenshot.PNG?raw=true)

### Настройка вида "Список функций" в Notepad++ для ассемблерных файлов
Удобную навигацию по меткам ассемлерного файла можно сделать следующим образом:

1. открываем файл 
%AppData%\Notepad++\functionList.xml
> если Notepad был установлен через инсталлятор важно открыть именно в папке %AppData%\Notepad++, а не из папки с notepad++.

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

Пример готового [functionList.xml](/Notepad++/functionList.xml) (можно просто заменить имеющийся)



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

![Light theme](/VisualStudio/Light_web.PNG?raw=true)

![Dark theme](/VisualStudio/Dark_web.PNG?raw=true)


## Sublime Text 3

Sublime Text 3 — свободный текстовый редактор с открытым исходным кодом для Windows с подсветкой синтаксиса большого количества языков программирования и разметки.

Поддерживаемые опции:
* Подсветка синтаксиса;

### Установка синтакиса "NeuroMatrix ASM"	 в Sublime Text 3

[Главное меню->Preferences->Browse Package] 

Откроется папка. Заходим в User и туда перекинуть файл NeuroMatrixASM.sublime-syntax

В меню [Главное меню->View->Syntax] должен появиться пункт "NeuroMatrix ASM" 