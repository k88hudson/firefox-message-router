# Website Recommendations

See [design overview](https://mozilla.invisionapp.com/share/JEQW8IBZHUV#/screens/353132813)

## Content

```ts
interface CFRContentProps {
  /** A sub-category of recommendations, like "cfrFeatures" */
  category?: string;
  /** Used for telemetry – A identifier for grouping multiple messages together in order to obfuscate their targeting information */
  bucket_id?: string;
  /** The text that shows in the URL bar in stage 1 */
  notification_text: string | {string_id: string};
  heading_text: string | {string_id: string};
  info_icon: {
    label: string | {string_id: string};
    sumo_path: string
  }
  text: string | {string_id: string};
  descriptionDetails?: {
    steps: Array<string | {string_id: string}>;
  }
  buttons: {
    primary: {
      label: string | {string_id: string};
      action: {type: string, data?: MessageManagerAllowedType};
    }
    secondary: [
      {
        label: string | {string_id: string};
        action: {type: string, data?: MessageManagerAllowedType};
      },
      {
        label: string | {string_id: string};
        action: {type: string, data?: MessageManagerAllowedType};
      },
      {
        label: string | {string_id: string};
        action: {type: string, data?: MessageManagerAllowedType};
      }
    ]
  }

}
```
