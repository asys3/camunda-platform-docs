---
id: process-instance-modification
title: Process instance modification
description: "An overview of process instance modification"
---

You may need to modify an active process instance to allow the execution to continue. The execution may be stuck and you may want to continue the execution on a different activity (i.e. skip or repeat activities).

## Modification mode

To enter modification mode, click the modify icon on the process instance header.

![enter-modification-mode](./img/modifications/enter-modification-mode.png)

The UI will change when you enter modification mode including a blue banner a the top and two buttons for applying or discarding modifications at the bottom.

![modification-mode](./img/modifications/modification-mode.png)

## Cancel all running tokens on a flow node

To cancel all the running tokens on a flow node, take the following steps:

1. Select the flow node you want to cancel all the running tokens on.

2. Click **Cancel** from the dropdown.

![cancel-token](./img/modifications/cancel-token.png)

3. See pending modification reflected in the instance history.

![cancel-token-result](./img/modifications/add-token-result.png)

## Add a new token to a flow node

To add a new token to a flow node, take the following steps:

1. Select the flow node you want to add the new token to.

2. Click **Add** from the dropdown.

![add-token](./img/modifications/add-token.png)

3. See pending modification reflected in the instance history.

![add-token-result](./img/modifications/add-token-result.png)

## Move all running tokens from one flow node to another

The move operation is equivalent to the combination of **Cancel** and **Add** modifications. The modifications described previously can also be achieved with one single move modification.

1. Select the flow node you want to move the running tokens from.

2. Click **Move** from the dropdown.

![move-token](./img/modifications/move-token.png)

3. Select the flow node you want to move the running tokens to.

![move-token-select-target](./img/modifications/move-token-select-target.png)

4. See pending modification reflected in the instance history.

![move-token-result](./img/modifications/move-token-result.png)

## Add variable to new scopes

During the modification mode if there are new scopes generated, it will be possible to add variables to these new scopes by following these steps:

1. Select the new scope from the instance history you want to add variable to.

![select-new-scope](./img/modifications/select-new-scope.png)

2. Click **Add Variable** button from the variables panel.

![add-variable-to-new-scope](./img/modifications/add-variable-to-new-scope.png)

3. Fill **Name** and **Value** fields for the variable you want to add.

4. Once you blur out of the field (click anywhere in the screen other than the last edited variable field), assuming the fields have the valid values, new variable will be added to the pending modifications.

![add-variable-result](./img/modifications/add-variable-result.png)

## Edit variable on existing scopes

During the modification mode it will be possible to edit existing variables in existing scopes by following these steps:

1. Select existing scope from the instance history that you want to edit variables on.

![edit-variable-on-existing-scope](./img/modifications/edit-variable-on-existing-scope.png)

2. Edit variable value from the variables panel.

![edit-variable-value](./img/modifications/edit-variable-value.png)

3. Once you blur out of the field (click anywhere in the screen other than the last edited variable field), assuming the new value is valid, **Edit Variable** modification will be added to the pending modifications.

![edit-variable-result](./img/modifications/edit-variable-result.png)

## View summary of pending modifications

In order to display the pending modifications, click **Apply Modifications** button from the footer.

![apply-modifications-button](./img/modifications/apply-modifications-button.png)

A modal will be displayed where all modifications can be seen.

![modification-summary-modal](./img/modifications/modification-summary-modal.png)

Within this modal you can to take following actions:

- (1): Delete any modification by clicking the **Delete Icon**.
- (2): View added variable in a JSON Viewer.
- (3): View edited variable in a Diff Viewer.
- (4): Cancel/close the modal and continue with modification mode.
- (5): Apply the modifications and exit modification mode.

## Undo modification

Clicking **Undo** from the modification footer will undo the latest modification.

![undo-modification](./img/modifications/undo-modification.png)

## Apply modifications

If you click the **Apply** button from the summary modal as described [here](#view-summary-of-pending-modifications), and modification operation is created successfully, you will see a success notification and changes will be reflected in a short time.

![applied-modifications](./img/modifications/applied-modifications.png)

## Non-supported modifications

Some elements do not support specific modifications:

- Elements within multi instance flow nodes are not supported for any kind of modification.
- **Add token** / **Move tokens to** modifications are not possible for the following type of elements:
  - Start events
  - Boundary events
  - Events attached to event-based gateways
- **Move tokens from** modification is not possible for a subprocess itself.
- **Add token** / **Move tokens to** modifications are currently not possible for elements that have multiple running scopes.

![not-supported-flow-nodes](./img/modifications/not-supported-flow-nodes.png)
