<script lang="ts">
	let { stepNo }: { stepNo: number } = $props()

	import RagPipeline from '$lib/rag-pipeline.svg?raw'
	import { onMount } from 'svelte'
	import { draggable } from '@neodrag/svelte'
	import { Transition } from '@animotion/core'

	let currentIndex = $state(0)
	const codeSnippets = [
		'Eliminate the production of unnecessary plastics, remove problematic additives, improve material choice to boost recyclability and reusability, and employ consistent labelling to avoid greenwashing.',
		'Establish a timebound strategy to reduce fossil fuel feedstock',
		'Companies should target zero routine flaring and eliminating methane emissions.',
		'Develop a heat energy decarbonisation plan and integrate it into the overall energy transition plan.'
	]
	let currentExample = $derived(codeSnippets[currentIndex])

	onMount(() => {
		const interval = setInterval(() => {
			currentIndex = (currentIndex + 1) % codeSnippets.length
		}, 3000)

		return () => clearInterval(interval)
	})
</script>

<div
	class="ml-10 xl:ml-20"
	style="--ask-opacity:{stepNo > 0 || stepNo == 0 ? '1' : '0.1'};
		   --initial-web-search-opacity:{stepNo > 1 || stepNo == 0 ? '1' : '0.1'};
		   --web-search-opacity:{stepNo > 2 || stepNo == 0 ? '1' : '0.1'};
           --scrape-opacity:{stepNo > 3 || stepNo == 0 ? '1' : '0.1'};
		   --ingest-opacity:{stepNo > 4 || stepNo == 0 ? '1' : '0.1'};
		   --retrieve-opacity:{stepNo > 5 || stepNo == 0 ? '1' : '0.1'};
		  --generate-opacity:{stepNo > 6 || stepNo == 0 ? '1' : '0.1'};
		 --feedback-opacity:{stepNo > 7 || stepNo == 0 ? '1' : '0.1'};
		 --answer-opacity:{stepNo > 8 || stepNo == 0 ? '1' : '0.1'};
		   "
>
	{@html RagPipeline}
</div>
{#if stepNo > 0}
<div class="top-0 left-0 absolute flex justify-center items-center w-screen h-screen pointer-events-none">
	<div
		use:draggable={{ bounds: 'body', cancel: '.cancel' }}
		class="left-10 absolute flex flex-col gap-4 backdrop-blur p-4 border-2 max-w-[35ch] max-h-[80%] overflow-auto text-sm xl:text-xl text-left cursor-grab pointer-events-auto"
		style="transition: unset !important; border-color: rgba(255, 255, 255, 0.5); box-shadow: 5px 5px 0px 0px rgba(37, 178, 100, 0.3); background-color: var(--cti-secondary);"
	>
		<div class="cursor-auto cancel">
			{#if stepNo == 1}
				<ul class="pl-5 list-none">
                    <li>
                        An example recommendation could be:
                        <p class="block mt-5 pl-5 border-l border-l-[var(--r-heading-color)]"><code class="text-xs xl:text-lg">{currentExample}</code></p>
                    </li>
                </ul>
			{/if}
			{#if stepNo == 2}
				<ul class="pl-5 list-none">
                    <li>
                        Pick a relevant organisation to analyse.
                    </li>
                </ul>
			{/if}
			{#if stepNo == 3}
				<ul class="pl-5 list-none">
					<li> Gather as many key policy documents as possible, such as annual reports, sustainability reports, and other relevant documents.</li>
					<!-- <li>
						Currently we use:
						<ul class="pl-5 list-disc">
							<li>Factset company reports.</li>
							<li>Bloomberg company reports and meeting transcripts.</li>
							<li>Manually curated documents.</li>
							<li>(soon) Web search/news</li>
						</ul>
					</li> -->
				</ul>
			{/if}
			{#if stepNo == 4}
				<ul class="pl-5 list-disc">
					<li>Download relevant documents.</li>
					<li>Convert PDFs to text, taking care to extract tables and charts correctly.</li>
				</ul>
			{/if}
			{#if stepNo == 5}
            <ul class="pl-5 list-disc">
                <li>Divide each document into semantic chunks and store them</li>
        </ul>
			{/if}
			{#if stepNo == 6}
            <ul class="pl-5 list-disc">
                <li>
                    Filter potential documents by organisation, type of document, and year of analysis.
                </li>
                <li>
                    Generate a number of queries to retrieve the most relevant chunks of text relevant to the recommendation.
                </li>
                </ul>
			{/if}
			{#if stepNo == 7}
            <ul class="pl-5 list-disc">
                <li>
                    For each year, independently pass the recommendation and all the organisation evidence to a LLM.
                </li>
				<li>
					Use LLM to extract key policy changes and actions taken by the organisation.
				</li>
				<li>Generate a score for each year, based on the evidence and the recommendation.</li>

                </ul>
			{/if}
			{#if stepNo == 8}
            <ul class="pl-5 list-disc">
                <li>
                    Manually verify the evidence and the score.
                </li>
                <li>
                    If not happy with the score, find more relevant documents through web search, contextualise the recommendation and repeat the process.
                </li>
                </ul>
			{/if}
			{#if stepNo == 9}
                    <ul class="pl-5 list-none">
									<ul class="pl-5 list-disc">
										<li>
											This tool is not perfect.
										</li>
										<li>
											But it gets the ball rolling.
										</li>
										<li>
						We can automate running many impact analyses for many different recommendations.
										</li>
										<li>
											To identify causal relationships, we use our audience analytics data (eg. Salesforce/Google Analytics).
										</li>
									</ul>
					</ul>
			{/if}
		</div>
	</div>
    </div>
{/if}
{#each { length: 9 } as _, i}
	<Transition
		do={() => {
			stepNo = i + 1
		}}
		undo={() => {
			stepNo = i
		}}
	/>
{/each}

<style>
    div {
        transition: all 0.5s ease;
    }
</style>