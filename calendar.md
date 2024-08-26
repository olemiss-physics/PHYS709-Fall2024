---
layout: page
title: Calendar
description: Listing of course modules and topics.
nav_order: 2
has_children: true
permalink: /calendar
---

# Calendar

The following is a **tentative** schedule that will change as the semester proceeds.
Make sure to keep an eye on the [Announcements]({{ site.baseurl }}{% link announcements.md %}) page.

#### Key
- **HW X**{: .label .label-yellow } : day homework X is assigned
- **HW Y**{: .label .label-red } : day homework Y is due (start of class)
- **CT Z**{: .label .label-cyan } : day computing task Z assigned
- **CT Z**{: .label .label-red } : day computing task Z is due (start of class)
- **G 1.1** : assigned reading from Goldstein section 1.1




<div class="module">
    <dl class="grid">
        <dt>Week</dt>
        <dd>
            <dl class="flex">
                <dt>Topics and Assignments</dt>
                <dd>Reading</dd>
            </dl>
        </dd>
    </dl>
</div>



{% for module in site.modules %}
{{ module }}
{% endfor %}
