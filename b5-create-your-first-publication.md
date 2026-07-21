# Create your first Publication

A Publication is the defined set of documentation Doc Holiday keeps current over time; see [Publications](/d1-publications.md). This guide covers the first setup in the app and shows how to choose Sources, a docs destination, and the right output types.

## Prerequisites

- At least one connected git repository Source; see [Connect GitHub](/b2-connect-github.md).
- One docs destination repository. A separate repository for docs is normal and recommended.
- Creating Publications requires an admin role — the **Add Publication** button is only shown to admins.

![The publication create form: name, source repositories, write destination, and output types](/screenshots/quickstart/publication-form.png)

1. Open **Publications** and select **Add Publication**. The **Create Publication** panel opens.
2. Enter a **Name** that makes the Publication easy to recognize later.
3. Under **Inputs** (**select all that apply**), choose the Sources this Publication should read from.
4. Under **Targets** (**select one**), choose the docs destination.
5. Under **Write:**, Doc Holiday starts **Documentation**, **Release Notes**, and **Changelog** on by default. For a first Publication, leave only **Documentation** on and turn **Release Notes** and **Changelog** off. See [Output types](/d3-output-types.md) for the broader explanation.
6. Leave **Commit Instructions** and **Writing Instructions** at their defaults for now.
7. Below Inputs the form shows a trigger section (**Add Triggering Event**). You can leave it empty for now; see [Configure triggers](/d2-configure-triggers.md). Finish by selecting **Save Changes**.

## Verify

Open the publication details view and confirm the **Status** section shows **Healthy**. Select **Run Test** to check it again.

## Next

Next: [request your first work](/f2-request-work-in-the-app.md).