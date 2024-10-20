---
title: Schema diff
subtitle: Learn how to use Neon's Schema Diff tool to compare branches of your database
enableTableOfContents: true
---

Neon's Schema Diff tool lets you compare an SQL script of the schemas for two selected branches in a side-by-side view (or line-by-line on mobile devices).

## How Schema Diff works

Schema Diff is available in the Neon Console for use in two ways:

- Compare a branch's schema to its parent
- Compare selected branches during a branch restore operation

### Compare to parent

In the detailed view for any child branch, you can check the schema differences between the selected branch and its parent. Use this view to verify the state of these schemas before you [Reset from parent](/docs/guides/reset-from-parent).

### Compare to another branch's history

Built into the Time Travel assist editor, you can use Schema Diff to help when restoring branches, letting you compare states of your branch against its own or another branch's history before you complete a [branch restore](/docs/guides/branch-restore) operation.

### Practical Applications

- **Pre-Migration Reviews**: Before migrating schemas from a development branch into main, use Schema Diff to ensure only intended schema changes are applied.
- **Audit Changes**: Historically compare schema changes to understand the evolution of your database structure.
- **Consistency Checks**: Ensure environment consistency by comparing schemas across development, staging, and production branches.

## How to Use Schema Diff

You can launch the Schema Diff viewer from the **Branches** and **Restore** pages in the Neon Console.

### From the Branches page

Open the detailed view for the branch whose schema you want to inspect. In the row of details for the parent branch, under the **COMPARE TO PARENT** block, click **Open schema diff**.

![Schema diff from branches page](/docs/guides/schema_diff_compare_parent.png)

### From the Restore page

Just like with [Time Travel Assist](/docs/guides/branch-restore#using-time-travel-assist), your first step is to choose the branch you want to restore, then choose where you want to restore from: **From history** (its own history) or ** From another branch** (from another branch's history).

Click the **Schema Diff** button, verify that your selections are correct, then click **Compare**.

The two-pane view shows the schema for both your target and your selected branches.

![schema diff results](/docs/guides/schema_diff_result.png)

### Understanding the Output

- **Green Highlight**: Indicates additions or new elements in the schema.
- **Red Highlight**: Marks deletions or removed elements from the schema.

## Tutorial

For a step-by-step guide showing you how to compare two development branches using Schema Diff, see [Schema diff tutorial](/docs/guides/schema-diff-tutorial).

## Limitations

Schema Diff is currently unable to compare branches that are protected under an IP Allow list. If you need to compare a protected branch, consider temporarily removing the IP Allow list to allow the Schema Diff comparison. Alternatively, if you are comparing non-primary branches, you can temporarily enable "Allow unrestricted access to non-primary branches" in the [IP Allow](/docs/manage/projects#configure-ip-allow) settings.
