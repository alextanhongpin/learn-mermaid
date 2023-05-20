# Best practices

## Sequence Diagram


- use `autonumber`
- use verb (no trailing `s`) when describing action, e.g. `send otp`, not `sends otp`
- remove actor when describing action, e.g. `request otp`, not `User request OTP`. The diagram already shows the actors and participants, so there is no need to repeat
- use `alt` to describe operation as black box - it can either be successful or failed.
	- there is no need to go into detail every step and interaction, as well as all possible failure scenario - that should be documented elsewhere
- avoid steps like `validate request` etc, we assume the requests are valid
