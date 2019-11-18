# Simple Calendar

[![Latest Stable Version](https://poser.pugx.org/donatj/simplecalendar/version)](https://packagist.org/packages/donatj/simplecalendar)
[![License](https://poser.pugx.org/donatj/simplecalendar/license)](https://packagist.org/packages/donatj/simplecalendar)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/donatj/SimpleCalendar/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/donatj/SimpleCalendar)
[![Code Coverage](https://scrutinizer-ci.com/g/donatj/SimpleCalendar/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/donatj/SimpleCalendar)
[![Build Status](https://travis-ci.org/donatj/SimpleCalendar.svg?branch=master)](https://travis-ci.org/donatj/SimpleCalendar)


A very simple, easy to use PHP calendar rendering class.

## Requirements

- **php**: >=5.5.0
- **ext-calendar**: *

## Installing

Install the latest version with:

```bash
composer require 'donatj/simplecalendar'
```

## Examples

```php
<?php

require '../vendor/autoload.php';

echo '<link rel="stylesheet" href="../src/css/SimpleCalendar.css" />';

$calendar = new donatj\SimpleCalendar('June 2010');

echo $calendar->render();

```

```php
<?php
require '../vendor/autoload.php';

echo '<link rel="stylesheet" href="../src/css/SimpleCalendar.css" />';

$calendar = new donatj\SimpleCalendar();

$calendar->setStartOfWeek('Sunday');
$calendar->addDailyHtml('Sample Event', 'today', 'tomorrow');

$calendar->setWeekDayNames([ 'Sun', 'Mon', 'Tu', 'W', 'Th', 'F', 'Sa' ]);
$calendar->setStartOfWeek('Monday');

echo $calendar->render();

```

## Documentation

### Class: \donatj\SimpleCalendar

Simple Calendar

#### Method: SimpleCalendar->__construct

```php
function __construct([ $calendarDate = null [, $today = null]])
```

##### Parameters:

- ***\DateTimeInterface*** | ***string*** | ***null*** `$calendarDate`
- ***\DateTimeInterface*** | ***string*** | ***bool*** | ***null*** `$today`

---

#### Method: SimpleCalendar->setDate

```php
function setDate([ $date = null])
```

Sets the date for the calendar.

##### Parameters:

- ***\DateTimeInterface*** | ***string*** | ***null*** `$date` - DateTimeInterface or Date string parsed by strtotime for the calendar
date. If null set to current timestamp.

---

#### Method: SimpleCalendar->setToday

```php
function setToday([ $today = null])
```

Sets "today"'s date. Defaults to today.

##### Parameters:

- ***\DateTimeInterface*** | ***string*** | ***null*** | ***bool*** `$today` - `null` will default to today, `false` will disable the
rendering of Today.

---

#### Method: SimpleCalendar->setWeekDayNames

```php
function setWeekDayNames([ array $weekDayNames = null])
```

##### Parameters:

- ***string[]*** | ***null*** `$weekDayNames`

---

#### Method: SimpleCalendar->addDailyHtml

```php
function addDailyHtml($html, $start_date_string [, $end_date_string = null])
```

Add a daily event to the calendar

##### Parameters:

- ***string*** `$html` - The raw HTML to place on the calendar for this event
- ***string*** `$start_date_string` - Date string for when the event starts
- ***string*** | ***null*** `$end_date_string` - Date string for when the event ends. Defaults to start date

---

#### Method: SimpleCalendar->clearDailyHtml

```php
function clearDailyHtml()
```

Clear all daily events for the calendar

---

#### Method: SimpleCalendar->setStartOfWeek

```php
function setStartOfWeek($offset)
```

Sets the first day of the week

##### Parameters:

- ***int*** | ***string*** `$offset` - Day the week starts on. ex: "Monday" or 0-6 where 0 is Sunday

---

#### Method: SimpleCalendar->show

```php
function show([ $echo = 'true'])
```

Returns/Outputs the Calendar

##### DEPRECATED

Use `render()` method instead.

##### Parameters:

- ***bool*** `$echo` - Whether to echo resulting calendar

##### Returns:

- ***string*** - HTML of the Calendar

---

#### Method: SimpleCalendar->render

```php
function render()
```

Returns the generated Calendar

##### Returns:

- ***string***