---
---
<details open>
<summary>
Why does this exist?
</summary>
Even though the imap protocoll is a widely used standard, it is outdated, insecure, and inflexible. It has been good for it's time when everyone hosted their own mail servers. With everyone moving to hosted cloud solutions like Gmail and Microsoft M365 / Outlook we should move towards their advanced API's to access emails hosted on their services. 

This is especially usefull and important for service providers that access an employees emails in display them in a separate interface.  CRM's, Task or Project Managers, and Service Desks are the primary culprits of only allowing for imap access.  However these tools often also allow for SSO via Google or Microsoft and thus should directly use their API's to access emails in an employees inbox.  
</details>

## The List

<table>
<thead>
<tr><th>Vendor</th><th>Google Login</th><th>Microsoft Login</th><th>Gmail API</th><th>Outlook API</th><th>Date Updated</th></tr>
</thead>
<tbody>
{% for vendor in site.data.vendors %}
<tr>
<td markdown="span"><a href="{{ vendor.url }}">{{ vendor.name }}</a></td>
<td markdown="span">{{ vendor.googleci }}</td>
<td markdown="span">{{ vendor.microsoftaad }}</td>
<td markdown="span">{{ vendor.gmailapi }}</td>
<td markdown="span">{{ vendor.outlookapi }}</td>
<!-- <td> 
  {% for source in vendor.pricing_source %}
  {% if forloop.first == false %}
  &amp;
  {% endif %}
<a href="{{ source }}">&#128279;</a>
{% endfor %}
{{ vendor.pricing_note }}</td> -->
<td>{{ vendor.updated_at }}</td>
</tr>
{% endfor %}
</tbody>
</table>

## FAQs

<details>
<summary>
I'm a vendor and I can't support all API's.
</summary>
We don't ask you to.  We ask you to support the two biggest API's on the market.  
</details>

<details>
<summary>
Google didn't allow listed my API endpoint. 
</summary>
This is a sign that your application does not fit basic security measures arount corporate data security and privacy.  You may want to really look at your security practices here.  
</details>

<details>
<summary>
What's so bad about imap? 
</summary>
For one, many administrators have turned it off by default.  Why?  Because we can't controll where emails end up.  We don't have controll over them in a secure and save manner. Allowing imap means that our employees may sign into our emails on insecure devices and download customer data to their personal, insecure devices.  We don't want to lose controll over those personal emails.  That's why we are turning imap off.  Additionally imap has been proven insecure <!--please amend data--> in transit and thus we like to have it turened off.  
</details>

<details>
<summary>
Why is API access better?  
</summary>
API access allows us as admins to monitor and allow list specific applications and add-ons while also being able to monitor their access using the build in logging tools.  
</details>

<details>
<summary>
I'm a vendor and this data is wrong!
</summary>
Please feel free to submit a PR to this page, or reach out at sso @ myGitHubUsername dotcom. I only want this data to be accurate.
</details>

## Footnotes
{% for vendor in site.data.vendors %}
{{ vendor.footnotes }}
{% endfor %}
