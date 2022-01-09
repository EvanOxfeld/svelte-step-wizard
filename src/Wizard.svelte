<script>
	import { setContext } from 'svelte'
	import { writable } from 'svelte/store'
	export let initialStep = 1
	
	let step = writable(initialStep)
	
	export const nextStep = () => {
			$step += 1
	}
	export const previousStep = () => {
			if ($step > 0) {
				$step -= 1	
			}
		}
	
	setContext('StepWizard', {
		step,
		nextStep,
		previousStep
	})
</script>

<slot nextStep={nextStep} previousStep={previousStep}></slot>
