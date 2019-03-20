# The lifecyle of a campaign

This section describes the process from campaign creation to when it displayed to users.

### What is a campaign?

A campaign is a message, or set of message variants, that communicates something to users. Some examples include:

* Recommending the Pinned Tabs feature to users who frequently use gmail
* Pointing out a new panel when users open devtools for the first time

## Step 1: Create a campaign specification

As a campaign author, you will need to decide on:

* a message type
* a template
* the content of the message (i.e. all the copy, images)
* the targeting, if requireing

This should be expressed in a specification document. If you are comfortable writing JSON, you can also skip directly to expressing your message using the “Standard Message Format”.

## Step 2: Get approval from Firefox Advocacy and Message UX stewards

In order to move forward with deploying your campaign, you will to get approval from the Firefox Advocacy and Message UX stewards. The best way to do this is to submit your campaign spec document (or annotated JSON) to Jessilyn Davis, the Message Router EPM.

## Step 3: Convert campaign to the Standard Message Format

If your campaign is approved, you will need to convert it to the Standard Message Format, which is an expression of a message, including its content, type, targeting, and timing, using JSON. Here is an example:

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

## Step 4: Deployment

After your JSON has been approved the Message Router team will upload your message to a secure remote service called Firefox Remote Settings. From there it will be dispatched to all targeted Firefox cients and users will see your campaign!

## Step 5: Data Analysis

Once your campaign is in production, you will be able to monitor Telemetry determine your next steps. You may choose to modify the campaign's targeting, expand its scope, or phase it out depending on what you learn.
