S – Situation:
While developing a form component to handle both adding and editing rules, I encountered a critical bug where form fields weren’t pre-filling correctly when switching to EDIT mode, even though the Redux state held the correct currentRule data.

T – Task:
My goal was to ensure that when the form was in EDIT mode, all fields, including dynamically generated ruleConditions, were accurately pre-filled using the data from the Redux store.

A – Action:

Initially, I built the form using hardcoded inputs with defaultValue set to currentRule.ruleConditions[index].configElementValue, but it didn’t behave as expected.

To improve structure, I converted the form into a dynamic one, using a JSON config to render inputs for all ruleConditions.

Tried using:

JSCODE
defaultValue={(isEdit && currentRule?.ruleConditions?.[index]?.configElementValue) || ""}
— but this alone didn’t work reliably, especially when Redux updated after the component mounted.

I then added a useEffect that:

Checked for isEdit and currentRule

Used setFormState(currentRule) to synchronously update the local form state

Reset the form when switching to ADD mode

R – Result:
This approach successfully resolved the pre-fill issue. The form now dynamically renders inputs and correctly syncs values from Redux, whether editing an existing rule or adding a new one. This also improved maintainability and scalability of the form logic.
