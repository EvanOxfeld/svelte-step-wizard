<script>
	import { getContext } from 'svelte'

	export let num
	
	const getStepWizardContext = () => {
		const context = getContext('StepWizard')
		if (!context) {
			throw new Error('StepWizard compound components cannot be rendered outside the StepWizard component')
		}
		return context
	}
	
	const { step, nextStep, previousStep } = getStepWizardContext()
</script>

{#if $step === num}
	<slot nextStep={nextStep} previousStep={previousStep}></slot>	
{/if}