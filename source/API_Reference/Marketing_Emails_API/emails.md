---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---

This endpoint allows you to manage entries in your Recipient Lists.


{% anchor h2 %} add {% endanchor %}


Add one or more emails to a Recipient List.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|
|list|Yes|Must be an existing Recipient List.|The list which you are adding email addresses too.|
|data|Yes|Must be a valid JSON string matching the required format. Limited to a 1000 entries maximum.|Specify the name, email address, and additional fields to add to the specified Recipient List.|

{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/add.json?list=Test&data=%7B%22email%22%3A%22example%40gmail.com%22%2C%22name%22%3A%22example%22%7D&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "inserted": 1
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane" id="add-xml">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/add.xml?list=Test&data=%7B%22email%22%3A%22example%40gmail.com%22%2C%22name%22%3A%22example%22%7D&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <inserted>1</inserted>
</result>

{% endcodeblock %}


#### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}


</div>
</div>
### Response

Success: (X records inserted)

{% codeblock %}{"inserted": X}{% endcodeblock %}

### Examples

Add an email recipient to a list:

{% codeblock %} \#curl -d 'api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=my_list&data={"email":"address@domain.com","name":"contactName"}' https://sendgrid.com/api/newsletter/lists/email/add.json {% endcodeblock %}

Add an email recipient with multiple data fields:

{% codeblock %}\#curl -d 'api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=my_list&data={"email":"grouch@trashcan.com","name":"Oscar","city":"New York","street":"123 Sesame St"}' https://sendgrid.com/api/newsletter/lists/email/add.json{% endcodeblock %}

Add multiple email recipients to a list:

{% codeblock %} \#curl -d 'api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=my_list&data[]={"email":"address1@domain.com","name":"contactName1"}&data[]={"email":"address2@domain.com","name":"contactName2"}' https://sendgrid.com/api/newsletter/lists/email/add.json {% endcodeblock %}

* * * * *


{% anchor h2 %} get {% endanchor %}


Get the email addresses and associated fields for a Recipient List.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|
|list|Yes|Must be an existing Recipient List.|The list you are searching.|
|email|No|Must be an email address or list of addresses.|Optional email addresses to search for in the Recipient List.|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/get.json?list=Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
[
  {
    "email": "dominic.may@sendgrid.com",
    "name": ""
  }
]
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/get.xml?list=Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<emails>
   <email>
      <email>dominic.may@sendgrid.com</email>
      <name> </name>
   </email>
</emails>

{% endcodeblock %}


#### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Remove one or more emails from a Recipient List.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
---
layout: page
weight: 0
title: Emails
navigation:
  show: true
---
-|
|list|Yes|Must be an existing Recipient List.|The list which you are removing email addresses from.|
|email|Yes|Must be an email or emails in the Recipient List.|Specify the email address or email addresses you wish to remove from the specified Recipient List.|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/delete.json?list=Test&email=example%40gmail.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "removed": 1
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/lists/email/delete.xml?list=Test&email=example%40gmail.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <removed>1</removed>
</result>

{% endcodeblock %}


#### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}


</div>
</div>
