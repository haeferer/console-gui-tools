## Classes

<dl>
<dt><a href="#ConsoleManager">ConsoleManager</a> ⇐ <code>EventEmitter</code></dt>
<dd></dd>
</dl>

## Constants

<dl>
<dt><a href="#Screen">Screen</a> : <code><a href="#Screen">Screen</a></code></dt>
<dd><p>The screen instance</p>
</dd>
<dt><a href="#stdOut">stdOut</a> : <code>PageBuilder</code></dt>
<dd><p>The logs page</p>
</dd>
<dt><a href="#homePage">homePage</a> : <code>PageBuilder</code></dt>
<dd><p>The main application</p>
</dd>
<dt><a href="#changeLayoutKey">changeLayoutKey</a> : <code>string</code></dt>
<dd><p>The key or combination to switch the selected page</p>
</dd>
<dt><a href="#layout">layout</a> : <code>DoubleLayout</code></dt>
<dd><p>The layout instance</p>
</dd>
</dl>

<a name="ConsoleManager"></a>

## ConsoleManager ⇐ <code>EventEmitter</code>
**Kind**: global class  
**Extends**: <code>EventEmitter</code>  

* [ConsoleManager](#ConsoleManager) ⇐ <code>EventEmitter</code>
    * [new ConsoleManager(options)](#new_ConsoleManager_new)
    * [.addGenericListeners()](#ConsoleManager+addGenericListeners)
    * [.setKeyListener(id, manageFunction)](#ConsoleManager+setKeyListener)
    * [.removeKeyListener(id)](#ConsoleManager+removeKeyListener)
    * [.registerWiget(widget)](#ConsoleManager+registerWiget)
    * [.unRegisterWidget(id)](#ConsoleManager+unRegisterWidget)
    * [.setHomePage(page)](#ConsoleManager+setHomePage)
    * [.refresh()](#ConsoleManager+refresh)
    * [.log(message)](#ConsoleManager+log)
    * [.error(message)](#ConsoleManager+error)
    * [.warn(message)](#ConsoleManager+warn)
    * [.info(message)](#ConsoleManager+info)
    * [.updateLogsConsole(reset)](#ConsoleManager+updateLogsConsole)
    * [.truncate(str, n, useWordBoundary)](#ConsoleManager+truncate)

<a name="new_ConsoleManager_new"></a>

### new ConsoleManager(options)
This class is used to manage the console GUI and all the widgets.


| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | The options of the ConsoleManager. |

**Example**  
```js
const CM = new ConsoleManager({ logPageSize: 10, layoutBorder: true, changeLayoutKey: 'ctrl+l', title: 'Console Application' })
```
<a name="ConsoleManager+addGenericListeners"></a>

### consoleManager.addGenericListeners()
This function is used to make the ConsoleManager handle the key events when no widgets are showed.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  
<a name="ConsoleManager+setKeyListener"></a>

### consoleManager.setKeyListener(id, manageFunction)
This function is used to set a key listener for a specific widget. The event listener is stored in the eventListenersContainer object.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The id of the widget. |
| manageFunction | <code>function</code> | The function to call when the key is pressed. |

**Example**  
```js
CM.setKeyListener('inputPopup', popup.keyListener)
```
<a name="ConsoleManager+removeKeyListener"></a>

### consoleManager.removeKeyListener(id)
This function is used to remove a key listener for a specific widget. The event listener is removed from the eventListenersContainer object.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The id of the widget. |

**Example**  
```js
CM.removeKeyListener('inputPopup')
```
<a name="ConsoleManager+registerWiget"></a>

### consoleManager.registerWiget(widget)
This function is used to register a widget. The widget is stored in the widgetsCollection object. That is called by the widgets in show().

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| widget | <code>Widget</code> | The widget to register. |

<a name="ConsoleManager+unRegisterWidget"></a>

### consoleManager.unRegisterWidget(id)
This function is used to unregister a widget. The widget is removed from the widgetsCollection object. That is called by the widgets in hide().

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The id of the widget. |

<a name="ConsoleManager+setHomePage"></a>

### consoleManager.setHomePage(page)
This function is used to set the home page. It also refresh the screen.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| page | <code>PageBuilder</code> | The page to set as home page. |

**Example**  
```js
CM.setHomePage(p)
```
<a name="ConsoleManager+refresh"></a>

### consoleManager.refresh()
This function is used to refresh the screen. It do the following sequence: Clear the screen, draw layout, draw widgets and finally print the screen to the stdOut.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  
**Example**  
```js
CM.refresh()
```
<a name="ConsoleManager+log"></a>

### consoleManager.log(message)
This function is used to log a message. It is used to log messages in the log page. Don't add colors to the message.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The message to log. |

**Example**  
```js
CM.log("Hello world")
```
<a name="ConsoleManager+error"></a>

### consoleManager.error(message)
This function is used to log an error message. It is used to log red messages in the log page. Don't add colors to the message.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The message to log. |

**Example**  
```js
CM.error("Anomaly detected")
```
<a name="ConsoleManager+warn"></a>

### consoleManager.warn(message)
This function is used to log a warning message. It is used to log yellow messages in the log page. Don't add colors to the message.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The message to log. |

**Example**  
```js
CM.warn("Anomaly detected")
```
<a name="ConsoleManager+info"></a>

### consoleManager.info(message)
This function is used to log an info message. It is used to log blue messages in the log page. Don't add colors to the message.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The message to log. |

**Example**  
```js
CM.info("Anomaly detected")
```
<a name="ConsoleManager+updateLogsConsole"></a>

### consoleManager.updateLogsConsole(reset)
This function is used to update the logs console. It is called by the log functions.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| reset | <code>boolean</code> | If true, the log scroll index is resetted. |

<a name="ConsoleManager+truncate"></a>

### consoleManager.truncate(str, n, useWordBoundary)
This function is used to truncate a string adding ... at the end.

**Kind**: instance method of [<code>ConsoleManager</code>](#ConsoleManager)  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | The string to truncate. |
| n | <code>number</code> | The number of characters to keep. |
| useWordBoundary | <code>boolean</code> | If true, the truncation will be done at the end of the word. |

**Example**  
```js
CM.truncate("Hello world", 5, true) // "Hello..."
```
<a name="Screen"></a>

## Screen : [<code>Screen</code>](#Screen)
The screen instance

**Kind**: global constant  
<a name="stdOut"></a>

## stdOut : <code>PageBuilder</code>
The logs page

**Kind**: global constant  
<a name="homePage"></a>

## homePage : <code>PageBuilder</code>
The main application

**Kind**: global constant  
<a name="changeLayoutKey"></a>

## changeLayoutKey : <code>string</code>
The key or combination to switch the selected page

**Kind**: global constant  
<a name="layout"></a>

## layout : <code>DoubleLayout</code>
The layout instance

**Kind**: global constant  