---
name: 'remix-single-route-module'
root: '.'
output: '**/*'
ignore: []
questions:
  name:
    message: 'Please enter a name.'
    initial: 'index'
  version:
    message: 'Please select a remix version.'
    choices:
      - 'v1'
      - 'v2'
    initial: 'v1'
---

# Variables

- componentName: `{{ inputs.name | pascal }}`
- fileName: `{{ inputs.name | camel }}`

# `{{ contains(inputs.version, 'v1') || "!" }}{{ fileName }}.tsx`

```tsx
import type { LoaderFunction} from "@remix-run/server-runtime";
import { redirect} from "@remix-run/server-runtime";
import { json } from "@remix-run/server-runtime";
import type { ActionFunction } from "@remix-run/server-runtime/dist/router";

export const loader: LoaderFunction = async ({ request }) => {
  return json({});
};

export const action: ActionFunction = async ({}) => {
  return redirect("/");
}

export default function {{ componentName }}Page() {
  return (
    <div>
      <h1>Index Page</h1>
    </div>
  )
}
```