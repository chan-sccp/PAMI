PAMI\Message\Response\AdvancedResponseMessage
===============

A generic SCCP response message from ami.

PHP Version 5


* Class name: AdvancedResponseMessage
* Namespace: PAMI\Message\Response
* Parent class: [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)



Constants
----------


### EOL

    const EOL = "\r\n"





### EOM

    const EOM = "\r\n\r\n"





Properties
----------


### $tables

    protected array<mixed,\PAMI\Message\Event\EventMessage> $tables

Child Tables



* Visibility: **protected**


### $temptable

    private Array $temptable

Catch All incoming Events into current Table.



* Visibility: **private**


### $events

    protected array<mixed,\PAMI\Message\Event\EventMessage> $events

Child events.



* Visibility: **protected**


### $completed

    protected boolean $completed

Is this response completed? (with all its events).



* Visibility: **protected**


### $rawContent

    protected string $rawContent

Holds original message.



* Visibility: **protected**


### $channelVariables

    protected array<mixed,string> $channelVariables

Metadata. Specific channel variables.



* Visibility: **protected**


### $statusVariables

    protected array<mixed,string> $statusVariables

Metadata. Specific channel variables.



* Visibility: **protected**


### $lines

    protected array<mixed,string> $lines

Message content, line by line. This is what it gets sent
or received literally.



* Visibility: **protected**


### $variables

    protected array<mixed,string> $variables

Metadata. Message variables (key/value).



* Visibility: **protected**


### $keys

    protected array<mixed,string> $keys

Metadata. Message "keys" i.e: Action: login



* Visibility: **protected**


### $createdDate

    protected integer $createdDate

Created date (unix timestamp).



* Visibility: **protected**


Methods
-------


### addEvent

    void PAMI\Message\Response\ResponseMessage::addEvent(\PAMI\Message\Event\EventMessage $event)

Adds an event to this response.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)


#### Arguments
* $event **[PAMI\Message\Event\EventMessage](PAMI-Message-Event-EventMessage.md)** - &lt;p&gt;Child event to add.&lt;/p&gt;



### hasTable

    boolean PAMI\Message\Response\AdvancedResponseMessage::hasTable()

Returns true if this Response Message contains an events tables (TableStart/TableEnd)



* Visibility: **public**




### getTableNames

    array<mixed,\PAMI\Message\Event\EventMessage> PAMI\Message\Response\AdvancedResponseMessage::getTableNames()

Returns all eventtabless for this response.



* Visibility: **public**




### getTable

    array<mixed,\PAMI\Message\Event\EventMessage> PAMI\Message\Response\AdvancedResponseMessage::getTable($tablename)

Returns all associated events for this response->tablename.



* Visibility: **public**


#### Arguments
* $tablename **mixed**



### getJSON

    array PAMI\Message\Response\AdvancedResponseMessage::getJSON()

Returns decoded version of the 'JSON' key if present.



* Visibility: **public**




### __construct

    void PAMI\Message\Message::__construct()

Constructor.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### __sleep

    array<mixed,string> PAMI\Message\Message::__sleep()

Serialize function.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### isComplete

    boolean PAMI\Message\Response\ResponseMessage::isComplete()

True if this response is complete. A response is considered complete
if it's not a list OR it's a list with its last child event containing
an EventList = Complete.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)




### getEvents

    array<mixed,\PAMI\Message\Event\EventMessage> PAMI\Message\Response\ResponseMessage::getEvents()

Returns all associated events for this response.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)




### isSuccess

    boolean PAMI\Message\Response\ResponseMessage::isSuccess()

Checks if the Response field has the word Error in it.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)




### isList

    boolean PAMI\Message\Response\ResponseMessage::isList()

Returns true if this response contains the key EventList with the
word 'start' in it. Another way is to have a Message key, like:
Message: Result will follow



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)




### getMessage

    string PAMI\Message\Response\ResponseMessage::getMessage()

Returns key: 'Privilege'.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)




### setActionId

    void PAMI\Message\Response\ResponseMessage::setActionId(string $actionId)

Sets an action id. This should not be necessary, but asterisk sometimes
decides to not send the Response: or Event: headers.



* Visibility: **public**
* This method is defined by [PAMI\Message\Response\ResponseMessage](PAMI-Message-Response-ResponseMessage.md)


#### Arguments
* $actionId **string** - &lt;p&gt;New ActionId.&lt;/p&gt;



### getEventList

    string PAMI\Message\IncomingMessage::getEventList()

Returns key 'EventList'. In respones, this will surely be a "start". In
events, should be a "complete".



* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)




### getRawContent

    string PAMI\Message\IncomingMessage::getRawContent()

Returns the original message content without parsing.



* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)




### getAllChannelVariables

    array PAMI\Message\IncomingMessage::getAllChannelVariables()

Returns the channel variables for all reported channels.

https://github.com/marcelog/PAMI/issues/85

The channel names will be lowercased.

* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)




### getChannelVariables

    array PAMI\Message\IncomingMessage::getChannelVariables(string $channel)

Returns the channel variables for the given channel.

https://github.com/marcelog/PAMI/issues/85

* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)


#### Arguments
* $channel **string** - &lt;p&gt;Channel name. If not given, will return variables
for the &quot;current&quot; channel.&lt;/p&gt;



### getAllStatusVariables

    array PAMI\Message\IncomingMessage::getAllStatusVariables()

Returns the channel variables for all reported channels.

https://github.com/marcelog/PAMI/issues/85

The channel names will be lowercased.

* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)




### getStatusVariables

    array PAMI\Message\IncomingMessage::getStatusVariables(string $channel)

Returns the channel variables for the given channel.

https://github.com/marcelog/PAMI/issues/85

* Visibility: **public**
* This method is defined by [PAMI\Message\IncomingMessage](PAMI-Message-IncomingMessage.md)


#### Arguments
* $channel **string** - &lt;p&gt;Channel name. If not given, will return variables
for the &quot;current&quot; channel.&lt;/p&gt;



### getCreatedDate

    integer PAMI\Message\Message::getCreatedDate()

Returns created date.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### setVariable

    void PAMI\Message\Message::setVariable(string $key, string $value)

Adds a variable to this message.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Variable name.&lt;/p&gt;
* $value **string** - &lt;p&gt;Variable value.&lt;/p&gt;



### getVariable

    string PAMI\Message\Message::getVariable(string $key)

Returns a variable by name.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Variable name.&lt;/p&gt;



### sanitizeInput

    \PAMI\Message\typed PAMI\Message\Message::sanitizeInput(string $value)

Sanitize incoming value



* Visibility: **protected**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $value **string** - &lt;p&gt;Key value.&lt;/p&gt;



### setKey

    void PAMI\Message\Message::setKey(string $key, string $value)

Adds a variable to this message.



* Visibility: **protected**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Key name (i.e: Action).&lt;/p&gt;
* $value **string** - &lt;p&gt;Key value.&lt;/p&gt;



### setSanitizedKey

    void PAMI\Message\Message::setSanitizedKey(string $key, string $value)

Adds a variable to this message after sanitizing it first.



* Visibility: **protected**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Key name (i.e: Action).&lt;/p&gt;
* $value **string** - &lt;p&gt;Key value.&lt;/p&gt;



### getKey

    string PAMI\Message\Message::getKey(string $key)

Returns a key by name.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Key name (i.e: Action).&lt;/p&gt;



### getBoolKey

    string PAMI\Message\Message::getBoolKey(string $key)

Returns a key by name.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string** - &lt;p&gt;Key name (i.e: Action).&lt;/p&gt;



### getKeys

    array<mixed,string> PAMI\Message\Message::getKeys()

Returns all keys for this message.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### getVariables

    array<mixed,string> PAMI\Message\Message::getVariables()

Returns all variabels for this message.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### finishMessage

    string PAMI\Message\Message::finishMessage($message)

Returns the end of message token appended to the end of a given message.



* Visibility: **protected**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $message **mixed**



### serializeVariable

    string PAMI\Message\Message::serializeVariable(string $key, string $value)

Returns the string representation for an ami action variable.



* Visibility: **private**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


#### Arguments
* $key **string**
* $value **string**



### serialize

    string PAMI\Message\Message::serialize()

Gives a string representation for this message, ready to be sent to
ami.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)




### getActionID

    string PAMI\Message\Message::getActionID()

Returns key: 'ActionID'.



* Visibility: **public**
* This method is defined by [PAMI\Message\Message](PAMI-Message-Message.md)


