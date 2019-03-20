# The Standard Message Format

The Standard Message Format is an expression of a message, including its content, type, targeting, and timing using JSON. Here is an example:

```js
{
 id: "PIN_TABS",
 message_type: "feature_callout",
 template: "cfr_general",
 content: {
   title: "Try Pinning a Tab",
   body: "Find a better example"
 },
 targeting: "hasFxAccount && !addonsInfo.addons['activity-stream@mozilla.org']",
 trigger: "visitSite(gmail.com)"
 frequency: {
   lifetime: 20,
   custom: [{period: "daily", cap: 5}, {period: 3600000, cap: 1}]
 }
}
```
