---
title: Create grants to authorize access to resources
description: Learn how to grant users and teams access to cluster resources with role-based access control.
keywords: rbac, ucp, grant, role, permission, authentication, authorization
redirect_from:
- /ucp/
ui_tabs:
- version: ucp-3.0
  orhigher: true
- version: ucp-2.2
  orlower: true
---

{% if include.ui %}
{% if include.version=="ucp-3.0" %}

UCP administrators can create *grants* to control how users and organizations
access resources.

## Kubernetes grants
With Kubernetes orchestration, a grant is made up of a *subject*, a *role*, and a
*namespace*.

This section is under construction.

{% elsif include.version=="ucp-2.2" %}
{% endif %}

## Swarm grants
With Swarm orchestration, a grant is made up of a *subject*, a *role*, and a
*resource collection*.

![](../images/ucp-grant-model-0.svg){: .with-border}

A grant defines who (subject) has how much access (role) to a set of resources
(collection). Each grant is a 1:1:1 mapping of subject, role, collection. For
example, you can grant the "Prod Team" "Restricted Control" permissions for the
"/Production" collection.

The usual workflow for creating grants has four steps.

1.  Set up your users and teams. For example, you might want three teams,
    Dev, QA, and Prod.
2.  Organize swarm resources into separate collections that each team uses.
3.  Optionally, create custom roles for specific permissions to the Docker API.
4.  Grant role-based access to collections for your teams.

![](../images/ucp-grant-model.svg){: .with-border}

### Create a Swarm grant

When you have your users, collections, and roles set up, you can create grants.
Administrators create grants on the **Manage Grants** page.

1.  Click **Create Grant**. All of the collections in the system are listed.
2.  Click **Select** on the collection you want to grant access to.
3.  In the left pane, click **Roles** and select a role from the dropdown list.
4.  In the left pane, click **Subjects**. Click **All Users** to create a grant
    for a specific user, or click **Organizations** to create a grant for an
    organization or a team.
5.  Select a user, team, or organization and click **Create**.

By default, all new users are placed in the `docker-datacenter` organization. If
you want to apply a grant to all UCP users, create a grant with the
`docker-datacenter` org as a subject.

## Where to go next

- [Isolate volumes between two different teams](isolate-volumes-between-teams.md)

{% endif %}