---
title: Squads
sidebar_position: 3
---

import DocCard from '@theme/DocCard';

## What are Internal Squads? {#whats-internal-squad}

Previously, we mentioned Config Profiles, which serve as complete Xray-core configuration templates for Nodes. When setting up a Node, you assign it a Profile and choose which of its Inbounds to activate.

If a Config Profile defines how a _Node_ behaves, an Internal Squad determines what a _user_ can access — think of it as an access control **group**.

Each Internal Squad allows you to select which Inbounds are available to users assigned to it. You can choose any Inbounds from any existing Config Profile, offering complete flexibility when defining user permissions.

Users can be assigned to multiple Internal Squads simultaneously, and this gives you fine control over user access.

This architecture allows you to create powerful combinations.

:::tip For example

- You might have one Squad for **regular users**, with access to specific Inbounds.
- And another for **premium users**, with access to additional Inbounds.

If a user is upgraded to premium, you simply assign them to both the premium and regular Squads.
:::

### Create an Internal Squad {#create-internal-squad}

Navigate to the `Internal Squads` page and either click `+` to create a new Squad, or `Edit` the default one.
<img src={require('./images/23.webp').default} width="100%" style={{borderRadius: '8px'}} alt="Internal Squad" />

In the menu that opens, you’ll see a list of all available Inbounds across all Config Profiles. From there, you can enable or disable specific ones for this Squad.  
Since we only have one available (`Shadowsocks`), go ahead and enable it, then click `Save`.

This configuration means that any user assigned to this Squad will only have access to the `Shadowsocks` Inbound.

At the moment, all Squads are empty — they don’t have any members yet.  
That’s because we haven’t created any users. In the next step, we’ll create a user and show you how to assign them to a Squad.

:::tip
You can **bulk**-manage Squad members by clicking the arrow next to the `Edit` button:

- `Add users` — assign all existing users to the Squad.
- `Remove users` — unassign all users currently in the Squad.

You can also see which Nodes are available to Squad members by clicking `View accessible nodes`.
:::

## What are External Squads? {#whats-external-squad}

Smart readers might have wondered, "If there are Internal Squads, where are External Squads?".

Since version 2.2.0, External Squads are implemented and are used to redefine the settings (e.g. Templates and the headers set in Subscription Settings) that users get.

For example, you can give some users a different `Announce` message to be displayed in clients.
Or you could apply custom routing per user group.

Essentially, External Squads are there to override Templates and other settings.

:::tip For example
- You might have one External Squad for **Iran**, with Templates specific to that country.
- And you might have another Squad for **China**, with appropriate configs given to users.
:::

### Create an External Squad {#create-external-squad}

Let's create an External Squad.

First, navigate to `External Squads` page. From there, press `+` button. Let's call it `Remnawave Supporters`.

A modal opens and we are given two tabs: `Templates` and `Settings`.

<img src={require('./images/45.webp').default} width="100%" style={{borderRadius: '8px'}} alt="External Squad Templates" />

In the `Templates` tab you can override the subscription Template. Currently, you can't choose anything and default Templates are selected. But worry not, once you created a new Template, you can return to this step.

<img src={require('./images/46.webp').default} width="100%" style={{borderRadius: '8px'}} alt="External Squad Settings" />

In the `Settings` tab you can override the subscription information that you defined in `Subscription` → `Settings`.

---

```mdx-code-block
<DocCard
  item={{ type: 'link', label: 'Users', description: 'We are finally ready to create a user.', href: '/docs/learn-en/users' }}
/>
```
