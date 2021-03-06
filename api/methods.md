---
description: Https methods
---

# Methods

## Overview

`base_url=https://api.labii.com/v1/`

## Common Methods

{% api-method method="get" host="" path="/\[app\]/\[table\]/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
\* List
{% endapi-method-summary %}

{% api-method-description %}
Querying a list of objects. See here \(https://docs.labii.com/api/overview\) for more details of app and table. The Parameters of Request and Response apply to all List Get methods.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="level" type="string" required=true %}
Read more at https://docs.labii.com/api/overview\#levels
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=true %}
Read more at https://docs.labii.com/api/overview\#url
{% endapi-method-parameter %}

{% api-method-parameter name="serializer" type="string" required=true %}
Read more at https://docs.labii.com/api/overview\#url
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
Authentification token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/organization/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Organization List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of organizations
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "days_available": 182,
    "add_permission": false,
    "change_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "username": "xxx",
            "description": "xxx",
            "logo_icon": "xxx",
            "logo_wordmark": "xxx",
            "is_academic": false,
            "is_subscription": true,
            "available_till": "2019-01-01",
            "payment": {
                "payment_option": "Subscription",
                "seats": 5,
                "available_till": "2019-01-01",
                "days_available": 180,
                "is_academic": "False",
                "credits": "$499.25"
            },
            "table_set": [
                {
                    "sid": "xxx",
                    "icon": "assignment",
                    "name_singular": "experiment",
                    "name_plural": "experiments",
                    "name_system": null,
                    "description": "An experiment is the lab note to document procedures carried out to support, refute, or validate a hypothesis.",
                    "unique_code": "EP",
                    "table_type": "Document",
                    "order": 1
                },
                ...
            ],
            "project_set": [
                {
                    "name": "xxx",
                    "sid": "xxx"
                },
                ...
            ],
            "widget_set": [
                {
                    "sid": "xxx",
                    "icon": "format_color_text",
                    "name": "Rich Text",
                    "subscription_price": "Free",
                    "PPU_price": "Free",
                    "notes": "Add Text with WYSIWYG Text Editor",
                    "component___status___WidgetActive": true,
                    "description": "Use this widget to add text from a WYSIWYG Text Editor. Other records can also be inserted via Mention(@).",
                    "instruction": "* To insert a link of other item, use <b>mention (@[Search Term])</b>. <br />- Type \"@\" to trigger suggestions. Click a list or press Enter to insert. Use \"__\" in search term to separate multiple keywords. For example, to find a experiment did by John, the mention term is <i>@ep__john</i><br />\r\n* To insert a consumption, use <b>mention (@[Amount]__[Unit]__of__[Search Term])</b>. For example, to insert the consumption of 10 ug of sample DNA: <i>@10__ug__of__sample__dna</i> <br />\r\n- The mentioned item can be a <i>Location</i>, consumption for all <i>Substance</i> in the location will be created. For example, to insert the consumption of 50 ul of all 96 miRNAs in a 96-well plate: <i>@50__ul__of__mirna__96__well__plate</i>",
                    "usecase": "",
                    "related_to": "",
                    "apply_to": "Substance,Document,File",
                    "allow_multiple": true,
                    "is_readonly": false,
                    "is_archived": false,
                    "is_public": true,
                    "date_updated": "2018-07-22T20:25:22.214763Z",
                    "date_created": "2018-01-03T05:31:33.477489Z"
                },
                ...
            ],
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/organizations/organization/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Organization List
{% endapi-method-summary %}

{% api-method-description %}
Add a new organization.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="level" type="string" required=true %}
user
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="serializer" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username of organization.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="seats" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
 {
    "sid": "xxx",
    "name": "xxx",
    "username": "xxx",
    "description": "xxx",
    "logo_icon": "xxx",
    "logo_wordmark": "xxx",
    "is_academic": false,
    "is_subscription": true,
    "available_till": "2019-01-01",
    "payment": {
        "payment_option": "Subscription",
        "seats": 5,
        "available_till": "2019-01-01",
        "days_available": 180,
        "is_academic": "False",
        "credits": "$499.25"
    },
    "table_set": [
        {
            "sid": "xxx",
            "icon": "assignment",
            "name_singular": "experiment",
            "name_plural": "experiments",
            "name_system": null,
            "description": "An experiment is the lab note to document procedures carried out to support, refute, or validate a hypothesis.",
            "unique_code": "EP",
            "table_type": "Document",
            "order": 1
        },
        ...
    ],
    "project_set": [
        {
            "name": "xxx",
            "sid": "xxx"
        },
        ...
    ],
    "widget_set": [
        {
            "sid": "xxx",
            "icon": "format_color_text",
            "name": "Rich Text",
            "subscription_price": "Free",
            "PPU_price": "Free",
            "notes": "Add Text with WYSIWYG Text Editor",
            "component___status___WidgetActive": true,
            "description": "Use this widget to add text from a WYSIWYG Text Editor. Other records can also be inserted via Mention(@).",
            "instruction": "* To insert a link of other item, use <b>mention (@[Search Term])</b>. <br />- Type \"@\" to trigger suggestions. Click a list or press Enter to insert. Use \"__\" in search term to separate multiple keywords. For example, to find a experiment did by John, the mention term is <i>@ep__john</i><br />\r\n* To insert a consumption, use <b>mention (@[Amount]__[Unit]__of__[Search Term])</b>. For example, to insert the consumption of 10 ug of sample DNA: <i>@10__ug__of__sample__dna</i> <br />\r\n- The mentioned item can be a <i>Location</i>, consumption for all <i>Substance</i> in the location will be created. For example, to insert the consumption of 50 ul of all 96 miRNAs in a 96-well plate: <i>@50__ul__of__mirna__96__well__plate</i>",
            "usecase": "",
            "related_to": "",
            "apply_to": "Substance,Document,File",
            "allow_multiple": true,
            "is_readonly": false,
            "is_archived": false,
            "is_public": true,
            "date_updated": "2018-07-22T20:25:22.214763Z",
            "date_created": "2018-01-03T05:31:33.477489Z"
        },
        ...
    ],
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
Wrong id: xxx. The sid does not match to user! - The sid does not match to token information
Wrong level: xxx. Acceptable levels is user. - Wrong level provided
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organization/detail/{sid}/" %}
{% api-method-summary %}
Organization Detail
{% endapi-method-summary %}

{% api-method-description %}
Get the organization object
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="sid" type="string" required=true %}
organization sid
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
 {
    "sid": "xxx",
    "name": "xxx",
    "username": "xxx",
    "description": "xxx",
    "logo_icon": "xxx",
    "logo_wordmark": "xxx",
    "is_academic": false,
    "is_subscription": true,
    "available_till": "2019-01-01",
    "payment": {
        "payment_option": "Subscription",
        "seats": 5,
        "available_till": "2019-01-01",
        "days_available": 180,
        "is_academic": "False",
        "credits": "$499.25"
    },
    "table_set": [
        {
            "sid": "xxx",
            "icon": "assignment",
            "name_singular": "experiment",
            "name_plural": "experiments",
            "name_system": null,
            "description": "An experiment is the lab note to document procedures carried out to support, refute, or validate a hypothesis.",
            "unique_code": "EP",
            "table_type": "Document",
            "order": 1
        },
        ...
    ],
    "project_set": [
        {
            "name": "xxx",
            "sid": "xxx"
        },
        ...
    ],
    "widget_set": [
        {
            "sid": "xxx",
            "icon": "format_color_text",
            "name": "Rich Text",
            "subscription_price": "Free",
            "PPU_price": "Free",
            "notes": "Add Text with WYSIWYG Text Editor",
            "component___status___WidgetActive": true,
            "description": "Use this widget to add text from a WYSIWYG Text Editor. Other records can also be inserted via Mention(@).",
            "instruction": "* To insert a link of other item, use <b>mention (@[Search Term])</b>. <br />- Type \"@\" to trigger suggestions. Click a list or press Enter to insert. Use \"__\" in search term to separate multiple keywords. For example, to find a experiment did by John, the mention term is <i>@ep__john</i><br />\r\n* To insert a consumption, use <b>mention (@[Amount]__[Unit]__of__[Search Term])</b>. For example, to insert the consumption of 10 ug of sample DNA: <i>@10__ug__of__sample__dna</i> <br />\r\n- The mentioned item can be a <i>Location</i>, consumption for all <i>Substance</i> in the location will be created. For example, to insert the consumption of 50 ul of all 96 miRNAs in a 96-well plate: <i>@50__ul__of__mirna__96__well__plate</i>",
            "usecase": "",
            "related_to": "",
            "apply_to": "Substance,Document,File",
            "allow_multiple": true,
            "is_readonly": false,
            "is_archived": false,
            "is_public": true,
            "date_updated": "2018-07-22T20:25:22.214763Z",
            "date_created": "2018-01-03T05:31:33.477489Z"
        },
        ...
    ],
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="/organization/detail/{sid}/" %}
{% api-method-summary %}
Organization Detail
{% endapi-method-summary %}

{% api-method-description %}
Partial update the organization information
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="sid" type="string" required=true %}
organization sid
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="name" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="logo\_icon" type="string" required=false %}
Icon logo picture data
{% endapi-method-parameter %}

{% api-method-parameter name="logo\_wordmark" type="string" required=false %}
Wordmark logo picture data
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
 {
    "sid": "xxx",
    "name": "xxx",
    "username": "xxx",
    "description": "xxx",
    "logo_icon": "xxx",
    "logo_wordmark": "xxx",
    "is_academic": false,
    "is_subscription": true,
    "available_till": "2019-01-01",
    "payment": {
        "payment_option": "Subscription",
        "seats": 5,
        "available_till": "2019-01-01",
        "days_available": 180,
        "is_academic": "False",
        "credits": "$499.25"
    },
    "table_set": [
        {
            "sid": "xxx",
            "icon": "assignment",
            "name_singular": "experiment",
            "name_plural": "experiments",
            "name_system": null,
            "description": "An experiment is the lab note to document procedures carried out to support, refute, or validate a hypothesis.",
            "unique_code": "EP",
            "table_type": "Document",
            "order": 1
        },
        ...
    ],
    "project_set": [
        {
            "name": "xxx",
            "sid": "xxx"
        },
        ...
    ],
    "widget_set": [
        {
            "sid": "xxx",
            "icon": "format_color_text",
            "name": "Rich Text",
            "subscription_price": "Free",
            "PPU_price": "Free",
            "notes": "Add Text with WYSIWYG Text Editor",
            "component___status___WidgetActive": true,
            "description": "Use this widget to add text from a WYSIWYG Text Editor. Other records can also be inserted via Mention(@).",
            "instruction": "* To insert a link of other item, use <b>mention (@[Search Term])</b>. <br />- Type \"@\" to trigger suggestions. Click a list or press Enter to insert. Use \"__\" in search term to separate multiple keywords. For example, to find a experiment did by John, the mention term is <i>@ep__john</i><br />\r\n* To insert a consumption, use <b>mention (@[Amount]__[Unit]__of__[Search Term])</b>. For example, to insert the consumption of 10 ug of sample DNA: <i>@10__ug__of__sample__dna</i> <br />\r\n- The mentioned item can be a <i>Location</i>, consumption for all <i>Substance</i> in the location will be created. For example, to insert the consumption of 50 ul of all 96 miRNAs in a 96-well plate: <i>@50__ul__of__mirna__96__well__plate</i>",
            "usecase": "",
            "related_to": "",
            "apply_to": "Substance,Document,File",
            "allow_multiple": true,
            "is_readonly": false,
            "is_archived": false,
            "is_public": true,
            "date_updated": "2018-07-22T20:25:22.214763Z",
            "date_created": "2018-01-03T05:31:33.477489Z"
        },
        ...
    ],
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/organizationmember/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
OrganizationMember List
{% endapi-method-summary %}

{% api-method-description %}
Return the members of the organization
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "email": "xxx@labii.com",
            "title": "xxx",
            "is_administrator": true,
            "is_archived": false,
            "date_start": "2018-01-01",
            "date_end": null,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
Wrong level: xxx. Acceptable levels is organization. - Wrong level provided
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/organizations/organizationmember/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
OrganizationMember List
{% endapi-method-summary %}

{% api-method-description %}
Create one or more new OrganizationMember objects.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="level" type="string" required=true %}
organization
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="serializer" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="email" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="date\_start" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="date\_end" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="is\_administrator" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="is\_archived" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "sid": "xxx",
    "name": "xxx",
    "email": "xxx@labii.com",
    "title": "xxx",
    "is_administrator": true,
    "is_archived": false,
    "date_start": "2018-01-01",
    "date_end": null,
    "change_permission": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
Wrong level: xxx. Acceptable levels is organization. - Wrong level provided
The fields organization, user must make a unique set. - Duplicated email
Your organization do not have enough seats to add new members. Contact sales@labii.com to increase seats.
Wrong email: xxx. Emails from academic or non-profile companies only. - For academic organization only
Error: The user (xxx) already exists! - Duplicated user
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/organizationmember/detail/{sid}/" %}
{% api-method-summary %}
OrganizationMember Detail
{% endapi-method-summary %}

{% api-method-description %}
Get the detail of a OrganizationMember object.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="sid" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "sid": "xxx",
    "name": "xxx",
    "email": "xxx@labii.com",
    "first_name": "xxx",
    "last_name": "xxx",
    "title": "xxx",
    "date_start": "2018-01-01",
    "date_end": null,
    "is_administrator": true,
    "is_archived": false,
    "change_permission": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="/organizations/organizationmember/detail/{sid}/" %}
{% api-method-summary %}
OrganizationMember Detail
{% endapi-method-summary %}

{% api-method-description %}
Update the data of a OrganizationMember object.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="sid" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="title" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="date\_start" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="date\_end" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="is\_administrator" type="boolean" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="is\_archived" type="boolean" required=false %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "sid": "xxx",
    "name": "xxx",
    "email": "xxx@labii.com",
    "first_name": "xxx",
    "last_name": "xxx",
    "title": "xxx",
    "date_start": "2018-01-01",
    "date_end": null,
    "is_administrator": true,
    "is_archived": false,
    "change_permission": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
You do not have permission to perform this action.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/team/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Team List
{% endapi-method-summary %}

{% api-method-description %}
Get list of teams
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "description": "xxx",
            "is_archived": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - The provided sid is not correct
Wrong level: xxx. Acceptable levels is user, organization. - Wrong level provided
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/organizations/team/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Team List
{% endapi-method-summary %}

{% api-method-description %}
Create a new team
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="level" type="string" required=true %}
organization
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="serializer" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="is\_archived" type="boolean" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="members" type="array" required=false %}
array of organization member sid
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "sid": "xxx",
    "name": "xxx",
    "description": "xxx",
    "members": [
        "xxx",
        "xxx"
    ],
    "is_archived": false,
    "change_permission": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Authentication credentials were not provided.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="" %}
{% api-method-summary %}
Team Detail
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="" %}
{% api-method-summary %}
Team Detail
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="" path="" %}
{% api-method-summary %}
Team Detail
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/organizationwidget/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Organization Widget List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of organization widgets
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "icon": "xxx",
            "name": "xxx",
            "notes": "xxx",
            "price": "Free",
            "show_in_menu": false,
            "order": 1,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/statement/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Statement List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of statements
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 2,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "date_start": "2018-07-27",
            "date_end": "2018-08-26",
            "subscription_cost": "$200.0",
            "ppu_cost": "$0",
            "widget_usage_cost": "$0.00",
            "record_storage_cost": "$0",
            "file_storage_cost": "$0",
            "total": "$200.0",
            "change_permission": false
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/organizations/backup/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Backup List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of backup
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 2,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "20180803031606.gz",
            "description": "Data backup on 20180803031606",
            "database_size": "47.0 MB",
            "date_created": "2018-08-03T03:17:41.438432Z",
            "change_permission": false
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/projects/project/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Project List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of projects
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "description": "xxx",
            "date_start": "2017-11-16",
            "date_end": null,
            "is_archived": false,
            "open_to_organization": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/projects/projectmember/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Project Member List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of members belong to a project
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 5,
    "next": null,
    "previous": null,
    "add_permission": false,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "permission": "Edit",
            "is_archived": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/table/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Table List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of tables
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 9,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "icon": "xxx",
            "name_singular": "experiment",
            "name_plural": "experiments",
            "unique_code": "EP",
            "table_type": "Document",
            "order": 1,
            "is_archived": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/column/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Column List
{% endapi-method-summary %}

{% api-method-description %}
Get list of columns belong to a table
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="table\_\_sid" type="string" required=false %}
The sid of a table
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 7,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "description": "xxx",
            "data_type": "Text",
            "default_value": null,
            "is_required": true,
            "is_hidden": false,
            "is_archived": true,
            "order": 1,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/filter/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Filter List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of filters
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 10,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "xxx",
            "description": null,
            "query": "name__icontains=2___[{\"field\": \"name\", \"expr\": \"icontains\", \"value\": \"2\"}]",
            "users": [],
            "is_archived": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/row/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Row List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of rows
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 1,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "369b0a40x29f50ejotyD",
            "name": "EP107: test file table display (v8)___test file table display",
            "rowdata_set": {
                "date_start___FILO0a40x1cHMRW27bg": "2018-07-26"
            },
            "project___project__sid": "Test___ehkn0a40x1glqvAFKP",
            "owner": "Yonggan Wu",
            "is_template": false,
            "open_to_organization": false,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/cell/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Cell List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of cells of a row
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 17,
    "count": 162,
    "next": "...",
    "previous": null,
    "add_permission": false,
    "results": [
        {
            "sid": "yBEH0a40x76ffAFKPUZ50",
            "widget": "Text",
            "record": "FL154: widgets-backlink-view  1.png",
            "change_permission": true
        },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/section/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Section List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of sections of a row
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 5,
    "count": 1,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "sid": "xxx",
            "name": "Double Signature",
            "widget___widget__sid": "xxx",
            "description": "",
            "is_archived": false,
            "order": 1,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=302 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/tables/version/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Version List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of versions
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 183,
    "count": 1829,
    "next": "http://127.0.0.1:8000/v1/tables/version/list/organization/ehkn0a40x1glqvAFKP/list/?page=2",
    "previous": null,
    "add_permission": false,
    "results": [
        {
            "sid": "xxx",
            "hash": "VGd4bzZhZmVhMzBkOWZlMmViNTdmZDE3YzBhOWVlMTUwYmMzSEZMcQ__",
            "previousHash": "WFFWbGRlMzViMmM1MzViZmM0MTdmYjU2N2FmZWFkYmFjOGJkWHFRSw__",
            "version": 8,
            "activity_message": "Updated data of Section (Files (No Preview)) from None to {\"files\": [{\"sid\": \"orux0a40x239qvAFKPUZ\", \"name\": \" FL143: FL154_ Small Workbook.xlsx (v3)\"}, {\"sid\": \"mpsv0a40x237otyDINSX\", \"name\": \" FL141: 2015-5-5 lib pool.xlsx (v3)\"}, {\"sid\": \"ehkn0a40x7dglqvAFKP\", \"name\": \" FL8: linkers and templates for subset-2.xlsx (v3)\"}]}",
            "is_valid": true,
            "updated_by": {
                "sid": "xxx",
                "first_name": "xxx",
                "last_name": "xxx",
                "email": "xxx@labii.com"
            },
            "date_created": "2018-07-27T07:10:57.279388Z",
            "change_permission": false
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/activities/activity/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Activity List
{% endapi-method-summary %}

{% api-method-description %}
Get a lis tof activities
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 232,
    "count": 2311,
    "next": null,
    "previous": null,
    "add_permission": true,
    "results": [
        {
            "icon": "edit",
            "user": {
                "sid": "xxx",
                "first_name": "xxx",
                "last_name": "xxx",
                "email": "xxx@labii.com"
            },
            "action": "Updated",
            "field": "data of Section (Files (No Preview))",
            "new_data": "{\"files\": [{\"sid\": \"xxx\", \"name\": \" FL143: xxx.xlsx (v3)\"}, {\"sid\": \"xxx\", \"name\": \" FL141: xxx.xlsx (v3)\"}, {\"sid\": \"xxx\", \"name\": \" FL8: xxx.xlsx (v3)\"}]}",
            "target": "Files (No Preview)",
            "model": "section",
            "object_sid": "xxx",
            "date_created": "2018-07-27T07:10:57.133353Z"
        },
        ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Wrong id - the provided sid is not correct
Wrong level - the provided level is not acceptable
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/widgets/widget/list/{level}/{sid}/{serializer}/" %}
{% api-method-summary %}
Widget List
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "page_size": 10,
    "page_number": 1,
    "page_count": 3,
    "count": 22,
    "next": null,
    "previous": null,
    "add_permission": false,
    "results": [
        {
            "sid": "xxx",
            "icon": "text_fields",
            "name": "Plain Text",
            "subscription_price": "Free",
            "PPU_price": "Free",
            "notes": "Add plain text, with markdown support",
            "usecase": "xxx",
            "related_to": "rich text",
            "allow_multiple": true,
            "is_readonly": false,
            "is_public": true,
            "component___status___WidgetActive": true,
            "change_permission": true
        },
        ...
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

