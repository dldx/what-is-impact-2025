<script lang="ts">
	import { Presentation, Slide, Transition, Action, getPresentation } from '@animotion/core'
	import Slide_1 from '$lib/components/slide_1.svelte'
	import Slide_2 from '$lib/components/slide_2.svelte'
	import RagPipeline from '$lib/RagPipeline.svelte'
	// Add data outputs state variables
	let layout = $state('')
	let visibility = $state('')
	let stepNo = $state(0)

	let slide1Ref: Slide_1
	let slide2Ref: Slide_2
</script>

<Presentation
	options={{
		history: true,
		transition: 'slide',
		controls: true,
		progress: true,

		width: 1920,
		height: 1080
	}}
>
	<!-- Title & Introduction -->
	<Slide class="place-content-center place-items-center h-full">
		<Transition visible>
			<div class="space-y-8 text-center">
				<h1
					class="drop-shadow-lg mb-8 max-w-3xl font-bold text-white text-6xl text-center leading-17"
				>
					What is impact <span class="text-[var(--cti-tertiary)]"> & how do we measure it?</span>
				</h1>
				<a
					class="font-bold text-white text-4xl hover:underline no-underline"
					href="https://www.linkedin.com/in/durand1/"
				>
					Durand D'souza
				</a>
			</div>
		</Transition>
	</Slide>
	<Slide
		class="place-content-center place-items-center h-full"
		in={() => {
			layout = ''
			slide1Ref.animate(0)
		}}
		out={() => {
			layout = ''
		}}
	>
		<Transition visible>
			<h1 class="static !text-yellow-300 text-5xl">How should we define impact?</h1>
			<h2 class="static text-3xl">Scenario 1</h2>
		</Transition>
		<Transition
			enter="enter"
			class="hidden"
			order={1}
			do={() => {
				layout = 'h-[60vh]'
				visibility = ''
				stepNo = 0
			}}
			undo={() => {
				layout = ''
				visibility = ''
			}}
		>
			<div class="{layout} m-16 flex flex-col place-content-center place-items-center">
				<Slide_1 bind:this={slide1Ref} {stepNo} />
			</div>

			<Action
				do={async () => {
					slide1Ref.animate(1)
				}}
				undo={async () => {
					slide1Ref.animate(0)
				}}
			/>
			<Action
				do={async () => {
					slide1Ref.animate(2)
				}}
				undo={async () => {
					slide1Ref.animate(1)
				}}
			/>

			<Action
				do={async () => {
					slide1Ref.animate(3)
				}}
				undo={async () => {
					slide1Ref.animate(2)
				}}
			/>
			<Action
				do={async () => {
					slide1Ref.animate(4)
				}}
				undo={async () => {
					slide1Ref.animate(3)
				}}
			/>
			<Action
				do={async () => {
					slide1Ref.animate(5)
				}}
				undo={async () => {
					slide1Ref.animate(4)
				}}
			/>
			<Action
				do={async () => {
					slide1Ref.animate(6)
				}}
				undo={async () => {
					slide1Ref.animate(5)
				}}
			/>
		</Transition>
	</Slide>
	<Slide
		class="place-content-center place-items-center h-full"
		in={() => {
			layout = ''
			slide2Ref.animate(0)
		}}
		out={() => {
			layout = ''
		}}
	>
		<Transition visible>
			<h1 class="static !text-yellow-300 text-5xl">How should we define impact?</h1>
			<h2 class="static text-3xl">Scenario 2</h2>
		</Transition>
		<Transition
			enter="enter"
			class="hidden"
			order={1}
			do={() => {
				layout = 'h-[60vh]'
				visibility = ''
				stepNo = 0
			}}
			undo={() => {
				layout = ''
				visibility = ''
			}}
		>
			<div class="{layout} m-16 flex flex-col place-content-center place-items-center">
				<Slide_2 bind:this={slide2Ref} {stepNo} />
			</div>

			<Action
				do={async () => {
					slide2Ref.animate(1)
				}}
				undo={async () => {
					slide2Ref.animate(0)
				}}
			/>
			<Action
				do={async () => {
					slide2Ref.animate(2)
				}}
				undo={async () => {
					slide2Ref.animate(1)
				}}
			/>

			<Action
				do={async () => {
					slide2Ref.animate(3)
				}}
				undo={async () => {
					slide2Ref.animate(2)
				}}
			/>
			<Action
				do={async () => {
					slide2Ref.animate(4)
				}}
				undo={async () => {
					slide2Ref.animate(3)
				}}
			/>
			<Action
				do={async () => {
					slide2Ref.animate(5)
				}}
				undo={async () => {
					slide2Ref.animate(4)
				}}
			/>
			<Action
				do={async () => {
					slide2Ref.animate(6)
				}}
				undo={async () => {
					slide2Ref.animate(5)
				}}
			/>
		</Transition>
	</Slide>
	<Slide
		class="place-content-center place-items-center h-full"
	>
		<Transition visible>
			<h1 class="static !text-yellow-300 text-5xl">Considerations</h1>
		</Transition>
		<Transition
			enter="enter"
			class="hidden"
			order={1}
			do={() => {
				layout = 'h-[60vh]'
				visibility = ''
				stepNo = 0
			}}
		>
		<div class="{layout} m-16 flex flex-col place-content-center place-items-center">
			<ul class="flex flex-col gap-12 pl-5 max-w-4xl text-left list-disc">
				<Transition enter="enter"><li>We may care about impact under all these scenarios</li></Transition>
				<Transition enter="enter"><li>But we cannot <strong>measure</strong> impact under all these scenarios</li></Transition>
				<Transition enter="enter"><li>Historically, we have inferred our impact on investors while failing to measure impact on polluters</li></Transition>
				<Transition enter="enter"><li>Making strategic decisions based on inferred impact is not sustainable</li></Transition>
			</ul>
		</div>
		</Transition>
	</Slide>
	<Slide
		class="place-content-center place-items-center h-full"
	>
		<Transition visible>
			<h1 class="static !text-yellow-300 text-5xl">
				Key Takeaway
			</h1>
				<p class="mt-12 max-w-xl text-3xl text-center">We need to focus on what we can measure and what ultimately counts towards impact which is <strong>emissions reductions & policy change</strong></p>
		</Transition>
	</Slide>
	<Slide
		class="place-content-center place-items-center h-full"
		in={() => (layout = '')}
		out={() => {
			layout = ''
		}}
	>
		<Transition visible>
			<h1 class="static !text-yellow-300 text-5xl">Automated impact tracking</h1>
		</Transition>
		<Transition
			enter="enter"
			class="hidden"
			order={1}
			do={() => {
				layout = 'h-[70vh]'
				visibility = ''
				stepNo = 1
			}}
			undo={() => {
				layout = ''
				visibility = ''
			}}
		>
			<div class="{layout} m-16 flex flex-col place-content-center place-items-center">
				<div
					class="{visibility} flex max-w-[50ch] flex-col place-content-center place-items-center text-sm xl:text-xl"
				>
					<Transition enter="fade-enter" class="mt-16">
						Which is why I built a tool to help us track impact.
					</Transition>
				</div>
				<Transition
					enter="fade-enter"
					class="w-[80vw] xl:w-[85vw] h-[80vh] xl:h-[85vh]"
					do={() => {
						visibility = 'hidden'
						stepNo = 0
						layout = 'h-[70vh]'
					}}
					undo={() => {
						visibility = ''
						stepNo = 0
						layout = 'h-[70vh]'
					}}
				>
					<RagPipeline {stepNo} />
				</Transition>
			</div>
		</Transition>
	</Slide>
	<Slide class="place-content-center place-items-center h-full">
		<Transition visible>
			<h1 class="static mb-12 !text-yellow-300 text-5xl">Summary</h1>
			<ul class="flex flex-col gap-12 pl-5 max-w-4xl text-left list-disc">
				<Transition enter="enter"><li>We need to be more intentional and strategic</li></Transition>
				<Transition enter="enter"><li>We need to focus on what we can measure and what ultimately counts towards impact</li></Transition>
				<Transition enter="enter"><li>We can automate much of the process of tracking impact and gathering evidence</li></Transition>
				<Transition enter="enter"><li>But we still need your help to make it better</li></Transition>
			</ul>
		</Transition>
	</Slide>


	<!-- Closing Slide -->
	<Slide
		class="place-content-center place-items-center h-full"
		out={() => {
			layout = 'h-[70vh]'
		}}
		in={() => {
			layout = ''
		}}
	>
		<Transition visible>
			<div class="space-y-12 max-w-4xl text-center">
				<h1 class="font-bold text-white text-6xl">Any questions?</h1>

				<div class="space-y-8">
					<Transition>
						<div class="space-y-6">
							<div class="bg-white/5 mt-6 p-6 border-[var(--cti-tertiary)] border-l-4">
								<h3 class="mb-4 font-semibold text-[var(--cti-tertiary)] text-2xl">Get in touch</h3>
								<div class="space-y-2 text-white text-lg">
									<p>
										<span class="font-semibold text-2xl">Durand D'souza</span>
									</p>
									<a
										href="https://www.linkedin.com/in/durand1/"
										class="flex flex-row justify-center items-center gap-2 font-semibold text-[var(--cti-tertiary)] hover:underline no-underline"
										target="_blank"
									>
										<svg
											xmlns="http://www.w3.org/2000/svg"
											width="24"
											height="24"
											viewBox="0 0 24 24"
											fill="none"
											stroke="currentColor"
											stroke-width="2"
											stroke-linecap="round"
											stroke-linejoin="round"
											class="lucide lucide-linkedin-icon lucide-linkedin"
											><path
												d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
											/><rect width="4" height="12" x="2" y="9" /><circle
												cx="4"
												cy="4"
												r="2"
											/></svg
										>
										durand1
									</a>
									<a
										href="https://bsky.app/profile/dldx.org"
										class="flex flex-row justify-center items-center gap-2 font-semibold text-[var(--cti-tertiary)] hover:underline no-underline"
										target="_blank"
									>
										<svg
											role="img"
											viewBox="0 0 24 24"
											fill="currentColor"
											stroke="none"
											width="24"
											height="24"
											xmlns="http://www.w3.org/2000/svg"
											><title>Bluesky</title><path
												d="M12 10.8c-1.087-2.114-4.046-6.053-6.798-7.995C2.566.944 1.561 1.266.902 1.565.139 1.908 0 3.08 0 3.768c0 .69.378 5.65.624 6.479.815 2.736 3.713 3.66 6.383 3.364.136-.02.275-.039.415-.056-.138.022-.276.04-.415.056-3.912.58-7.387 2.005-2.83 7.078 5.013 5.19 6.87-1.113 7.823-4.308.953 3.195 2.05 9.271 7.733 4.308 4.267-4.308 1.172-6.498-2.74-7.078a8.741 8.741 0 0 1-.415-.056c.14.017.279.036.415.056 2.67.297 5.568-.628 6.383-3.364.246-.828.624-5.79.624-6.478 0-.69-.139-1.861-.902-2.206-.659-.298-1.664-.62-4.3 1.24C16.046 4.748 13.087 8.687 12 10.8Z"
											/></svg
										>
										dldx.org
									</a>
								</div>
							</div>
						</div>
					</Transition>
				</div>
			</div>
		</Transition>
	</Slide>
</Presentation>
