<!-- --- title: urn:ietf:params:xml:ns:caldav:max-date-time -->
<!-- --- link_title: CALDAV:max-date-time -->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 5.2.7 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: max-date-time -->
<!-- --- type: property -->
<!-- --- purpose:  Provides a DATE-TIME value indicating the latest date and time (in UTC) that the server is willing to accept for any DATE or DATE-TIME value in a calendar object resource stored in a calendar collection. -->
<!-- --- value: An iCalendar format DATE-TIME value in UTC -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:caldav:calendar]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a DATE-TIME value indicating the latest date and time (in UTC) that the server is willing to accept for any DATE or DATE-TIME value in a calendar object resource stored in a calendar collection.

###Value
An iCalendar format DATE-TIME value in UTC

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:max-date-time is used to specify an iCalendar DATE-TIME value in UTC that indicates the inclusive latest date that the server is willing to accept for any date or time value in a calendar object resource stored in a calendar collection.  Any attempt to store a calendar object resource using a DATE or DATE-TIME value later than this value MUST result in an error, with the CALDAV:max-date-time precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated.  Note that servers MUST accept recurring components that specify instances beyond this limit, provided none of those instances have been overridden. In that case, the server MAY simply ignore those instances outside of the acceptable range when processing reports on the calendar object resource. In the absence of this property, the client can assume any valid iCalendar date may be used at least down to the CALDAV:min-date-time value, if that is defined.

### DTD
> 
```
<!ELEMENT max-date-time (#PCDATA)>
PCDATA value: an iCalendar format DATE-TIME value in UTC
```

###Example
> 
>
```xml
<C:max-date-time xmlns:C="urn:ietf:params:xml:ns:caldav"
>20491231T235959Z</C:max-date-time>
```
