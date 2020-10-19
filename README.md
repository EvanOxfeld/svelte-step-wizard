# svelte-step-wizard

Simple Svelte step wizard component

## Install

```bash
npm i svelte-step-wizard
```

## Example

[REPL Example](https://svelte.dev/repl/e39c6f095d954ee38389253c31a82b4c?version=3.29.0)

```svelte
<script>
	import StepWizard from 'svelte-step-wizard'
</script>

<StepWizard initialStep={1}>
	<StepWizard.Step num={1} let:nextStep>
		<p>
			This is the first step.
		</p>
		<button on:click={nextStep}>
			Next Step	>
		</button>
	</StepWizard.Step>
	<StepWizard.Step num={2} let:previousStep let:nextStep>
		<p>
			Keep going.
		</p>
		<button on:click={previousStep}>
			Go Back
		</button>
		<button on:click={nextStep}>
			Next Step	>
		</button>
	</StepWizard.Step>
	<StepWizard.Step num={3} let:previousStep>
		<p>
			Done!
		</p>
		<button on:click={previousStep}>
			Go Back
		</button>
	</StepWizard.Step>
</StepWizard>
```

