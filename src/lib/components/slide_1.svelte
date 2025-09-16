<script lang="ts">
	import { tween, all } from '@animotion/motion'
	const arrow = tween({ opacity: 0, width: 0 }, { duration: 500 })
	const polluter = tween({ y: -500, opacity: 0 }, { duration: 500 })
	const smoke = tween({ opacity: 1 }, { duration: 500 })
	const smokestack = tween({ y: 0 }, { duration: 500 })
	const partialsmoke = tween({ opacity: 1 }, { duration: 500 })
	const impact = tween({ opacity: 0, scale: 1 }, { duration: 500 })
	let { stepNo }: { stepNo: number } = $props()
	export async function animate(stepNo: number) {
		if (stepNo == 0) {
			// hide arrow
			await arrow.to({ opacity: 0 })
			// hide polluter
			await polluter.to({ y: -500, opacity: 0 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// show smokestack
			await smokestack.to({ y: 0 })
			// show partial smoke
			await partialsmoke.to({ opacity: 1 })
            // Hide impact
            await impact.to({ opacity: 0 })
		}
		if (stepNo == 1) {
			// hide arrow
			await arrow.to({ opacity: 0 })
			// show polluter
			await polluter.to({ y: 0, opacity: 1 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// show smokestack
			await smokestack.to({ y: 0 })
			// show partial smoke
			await partialsmoke.to({ opacity: 1 })
		}
		if (stepNo == 2) {
			// show arrow
			await arrow.to({ opacity: 1, width: 1 })
			// show polluter
			await polluter.to({ y: 0, opacity: 1 })
			// show smokestack
			await smokestack.to({ y: 0 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// show partial smoke
			await partialsmoke.to({ opacity: 1 })
		}
		if (stepNo == 3) {
			// show arrow
			await arrow.to({ opacity: 1, width: 1 })
			// show polluter
			await polluter.to({ y: 0, opacity: 1 })
			// hide smoke
			await smoke.to({ opacity: 0 }, { duration: 1000 })
			// hide smokestack
			await smokestack.to({ y: -1500 }, { duration: 1000 })
			// show partial smoke
			await partialsmoke.to({ opacity: 1 })
        }
        if (stepNo == 4) {
            // show impact
            await impact.to({ opacity: 1, scale: 1 })
		}
		if (stepNo == 5) {
            // hide impact
            await impact.to({ opacity: 0 }, { duration: 500 })
			// show smokestack
			await smokestack.to({ y: 0 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// hide partial smoke
			await partialsmoke.to({ opacity: 0 }, { duration: 500, delay: 500 })
		}
		if (stepNo == 6) {
			// show impact
			await impact.to({ opacity: 1 })
            await impact.to({ scale: 0.7 }, { duration: 500, delay: 500 })
		}
	}
</script>

<svg
	width="1012.7"
	height="378.85"
	version="1.1"
	viewBox="0 0 506.36 189.43"
	xmlns="http://www.w3.org/2000/svg"
	xmlns:xlink="http://www.w3.org/1999/xlink"
    overflow="visible"
>
	<!-- svg-source:excalidraw -->
	<defs>
		<style class="style-fonts">
			@font-face {
				font-family: Excalifont;
				src: url(data:font/woff2;base64,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);
			}
		</style>
		<clipPath id="SVGID_00000045615448653943012690000000638754117711156656_">
			<use xlink:href="#SVGID_1_" />
		</clipPath>
		<path
			id="SVGID_1_"
			d="m847.5 617.48c0 136.96-111.03 248-248 248-136.97 0-248-111.03-248-248 0-136.97 111.04-248 248-248 136.97 0 248 111.04 248 248z"
		/>
	</defs>
	<mask id="mask-image-crop-wXzwZ5s162Swzbn-HDebe" fill="#fff">
		<rect x="35.34" y="55.189" width="166" height="146" />
	</mask>
	<g transform="translate(-25.34 -21.963)" mask="url(#mask-image-crop-wXzwZ5s162Swzbn-HDebe)">
		<use
			width="201.34012"
			height="201.18867"
			href="#image-crop-413635151d9e6ef5ac51a63e2bd501140953e76e9f7c606fa2f8a78e45d8d5b6ef0a524bba2a68f0b44dda5286d8ee8c-2426746997"
		/>
	</g>
	<g transform="translate(23.145 15.66) rotate(0 69.88 12.5)">
		<text
			y="17.620001"
			dominant-baseline="alphabetic"
			fill="#f08c00"
			font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
			font-size="20px"
			style="white-space:pre"
			><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'">Tracker Group</tspan
			></text
		>
	</g>
	<g
		stroke-linecap="round"
		id="arrow"
		style:opacity={arrow.opacity}
		style:transform="scaleX({arrow.width})"
		style="transform-origin: left center;"
	>
		<g transform="translate(189.02 77.887)">
			<text
				x="-23.742607"
				y="15.879724"
				dominant-baseline="alphabetic"
				fill="white"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				font-size="20px"
				style="white-space:pre"
				><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
					>Don't pollute please</tspan
				></text
			>
		</g>
		<g
			transform="translate(164.03 103.69) rotate(0 95.293 1.7346)"
			fill="none"
			stroke="#f08c00"
			stroke-width="2"
		>
			<path
				d="m-1.98 3.9c61.73-8.13 119.49-1.72 194.54-3.96m-193.85 1.11c67.5-3.4 135.12 0.09 191.19 0.21"
			/>
			<path
				d="m165.3 11.43c9.01-6.39 16.03-5.84 26.39-10.59m-26.05 9.17c8.52-4.25 17.03-5.58 24.72-8.51"
			/>
			<path
				d="m165.54-5.67c8.91-1.12 15.86 4.71 26.15 6.51m-25.81-7.93c8.32 1.86 16.75 6.63 24.48 8.59"
			/>
		</g>
	</g>
	<mask />
	<g id="polluter" transform="translate(0 {polluter.y})" style:opacity={polluter.opacity}>
		<g transform="translate(389.7 17.843)">
			<text
				y="17.620001"
				dominant-baseline="alphabetic"
				fill="#f08c00"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				font-size="20px"
				style="white-space:pre"
				><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'">Polluter</tspan
				></text
			>
		</g>
		<g id="OBJECTS" transform="matrix(.27367 0 0 .27367 354.07 36.623)" stroke-width="1.827">
			<path
				d="m461.63 390.71c0-116.88-94.749-211.63-211.63-211.63s-211.63 94.749-211.63 211.63"
				fill="#ffde25"
			/>
			<g transform="translate(-3.654)">
				<polyline
					points="258.3 330.16 297.57 299.69 326.04 319.89 369.88 292.55 426.41 334.94 423.61 359.95 278.07 366.29"
					fill="#fbb62d"
				/>
				<g fill="#4e8d3a">
					<path
						d="m353.01 367.45c-0.088 0-0.178-8e-3 -0.268-0.023-0.815-0.147-1.357-0.928-1.21-1.742 6.411-35.573-9.422-56.815-9.583-57.025-0.502-0.658-0.377-1.6 0.28-2.103 0.656-0.502 1.596-0.381 2.101 0.277 0.689 0.898 16.814 22.431 10.154 59.381-0.13 0.726-0.762 1.235-1.474 1.235z"
					/>
					<path
						d="m346.53 313.39s4.52-10.143-7.888-11.453c-2.181 12.019 7.888 11.453 7.888 11.453z"
					/>
					<path
						d="m349.63 319.82s10.878 2.231 9.487-10.168c-12.206 0.457-9.487 10.168-9.487 10.168z"
					/>
					<path d="m349.83 319.59s-6.975-8.64-13.788 1.813c9.71 7.411 13.788-1.813 13.788-1.813z" />
					<path
						d="m352.38 330.66s9.958 4.914 11.753-7.433c-11.924-2.65-11.753 7.433-11.753 7.433z"
					/>
					<path
						d="m352.63 330.49s-4.56-10.125-13.798-1.739c7.516 9.628 13.798 1.739 13.798 1.739z"
					/>
					<path d="m354.2 343.72s8.977 6.536 12.847-5.325c-11.3-4.64-12.847 5.325-12.847 5.325z" />
					<path
						d="m354.48 343.59s-2.771-10.753-13.301-4.061c5.769 10.767 13.301 4.061 13.301 4.061z"
					/>
				</g>
				<g fill="#6ea843">
					<path
						d="m431.43 334.42c-0.213 0-0.43-0.046-0.637-0.142-0.75-0.352-1.072-1.245-0.72-1.995 15.957-33.986 41.569-42.211 42.651-42.545 0.791-0.239 1.629 0.199 1.874 0.99s-0.198 1.631-0.989 1.876c-0.253 0.079-25.459 8.235-40.82 40.954-0.256 0.544-0.796 0.862-1.359 0.862z"
					/>
					<path
						d="m467.13 293.82s2.185-10.887 13.062-4.774c-5.179 11.063-13.062 4.774-13.062 4.774z"
					/>
					<path
						d="m460.88 297.27s-10.162-4.477-1.851-13.783c9.689 7.438 1.851 13.783 1.851 13.783z"
					/>
					<path
						d="m460.85 296.97s10.689-3.008 10.195 9.459c-12.208 0.423-10.195-9.459-10.195-9.459z"
					/>
					<path
						d="m452.37 304.52s-10.964-1.757-5.282-12.864c11.258 4.74 5.282 12.864 5.282 12.864z"
					/>
					<path
						d="m452.26 304.23s9.579-5.617 12.258 6.568c-11.702 3.502-12.258-6.568-12.258-6.568z"
					/>
					<path
						d="m443.33 314.12s-11.103 0.134-7.394-11.778c11.9 2.756 7.394 11.778 7.394 11.778z"
					/>
					<path
						d="m443.17 313.85s8.483-7.165 13.197 4.387c-10.936 5.441-13.197-4.387-13.197-4.387z"
					/>
					<path
						d="m333.33 270.29c0-14.337-11.622-53.19-25.959-53.19s-25.959 38.853-25.959 53.19 11.622 25.959 25.959 25.959 25.959-11.622 25.959-25.959z"
					/>
				</g>
				<g fill="#13304e">
					<path
						d="m307.37 333.28c-0.829 0-1.5-0.672-1.5-1.5v-73.128c0-0.828 0.671-1.5 1.5-1.5s1.5 0.672 1.5 1.5v73.128c0 0.828-0.672 1.5-1.5 1.5z"
					/>
					<path
						d="m307.37 290c-0.38 0-0.761-0.144-1.053-0.432l-9.709-9.567c-0.59-0.581-0.597-1.531-0.016-2.121s1.531-0.597 2.121-0.016l9.709 9.567c0.59 0.581 0.597 1.531 0.016 2.121-0.293 0.298-0.681 0.448-1.068 0.448z"
					/>
					<path
						d="m307.37 276.4c-0.383 0-0.765-0.145-1.058-0.437-0.587-0.585-0.589-1.534-5e-3 -2.121l6.634-6.667c0.585-0.588 1.534-0.59 2.122-6e-3 0.587 0.585 0.589 1.534 5e-3 2.121l-6.634 6.667c-0.294 0.296-0.679 0.443-1.064 0.443z"
					/>
					<path
						d="m307.37 311.23c-0.43 0-0.856-0.184-1.153-0.54-0.53-0.636-0.444-1.582 0.192-2.112l8.043-6.702c0.638-0.53 1.583-0.444 2.113 0.192s0.444 1.582-0.192 2.112l-8.043 6.702c-0.282 0.234-0.622 0.348-0.96 0.348z"
					/>
				</g>
				<path
					d="m351.8 273.6c0-18.435 14.944-68.392 33.379-68.392s33.379 49.958 33.379 68.392-14.944 33.379-33.379 33.379-33.379-14.944-33.379-33.379z"
					fill="#6ea843"
				/>
				<g fill="#13304e">
					<path
						d="m385.17 354.16c-0.829 0-1.5-0.672-1.5-1.5v-94.029c0-0.828 0.671-1.5 1.5-1.5s1.5 0.672 1.5 1.5v94.029c0 0.828-0.671 1.5-1.5 1.5z"
					/>
					<path
						d="m385.17 298.52c-0.388 0-0.775-0.149-1.068-0.447-0.581-0.59-0.575-1.54 0.016-2.121l12.484-12.301c0.589-0.582 1.54-0.574 2.121 0.016 0.582 0.59 0.575 1.54-0.016 2.121l-12.484 12.301c-0.292 0.288-0.673 0.431-1.053 0.431z"
					/>
					<path
						d="m385.17 281.03c-0.385 0-0.77-0.147-1.063-0.442l-8.531-8.572c-0.584-0.587-0.582-1.536 5e-3 -2.121 0.587-0.583 1.537-0.582 2.122 6e-3l8.531 8.572c0.584 0.587 0.582 1.536-5e-3 2.121-0.293 0.291-0.676 0.436-1.059 0.436z"
					/>
					<path
						d="m385.17 325.82c-0.338 0-0.679-0.114-0.96-0.348l-10.342-8.618c-0.636-0.53-0.722-1.477-0.192-2.112 0.53-0.637 1.475-0.723 2.113-0.192l10.342 8.618c0.636 0.53 0.722 1.477 0.192 2.112-0.297 0.357-0.723 0.54-1.153 0.54z"
					/>
				</g>
				<path
					d="m447.73 347.09c0.318-11.124-3.002-21.627-10.618-26.635-16.495-10.847-42.552 0-40.342 22.34-28.737-4.509-30.013 16.786-30.013 16.786s-8.671-15.592-29.671-4.36c1.105-24.689-21-39.416-40.342-27.604-11.053-34.609-46.745-37.746-46.745-37.746v91.359l172.03-0.383c3.984 6.781 11.35 1.274 19.783 1.274 12.666 0 22.934-0.206 22.934-12.872 1e-3 -10.619-7.217-19.548-17.013-22.159z"
					fill="#4e8d3a"
				/>
				<path
					d="m449.08 370.51c0 14.01-11.357 16.723-25.366 16.723s-25.367-2.714-25.367-16.723c0-14.01 11.357-25.367 25.367-25.367s25.366 11.358 25.366 25.367z"
					fill="#13304e"
					opacity=".2"
				/>
				<path
					d="m383.47 377.39s-9.577-8.476-7.729-11.43 8.905 3.935 8.905 3.935-6.889-11.634-2.352-13.714 6.889 11.53 6.889 11.53 1.344-11.085 5.041-10.245c3.696 0.84 0.168 13.32 0.168 13.32s3.865-8.843 7.393-7.555c3.528 1.287-4.369 15.052-4.369 15.052"
					fill="#6ea843"
				/>
				<path d="m250 378.28v-43.814s47.85-7.55 51.166 43.814" fill="#13304e" opacity=".2" />
				<path
					d="m251.63 376.15s1.215-23.439 6.251-23.526c5.035-0.087 2.604 15.912 2.604 15.912s4.256-15.912 8.966-14.103c4.351 1.671-3.658 15.629-3.658 15.629s8.48-9.22 11.535-5.997c3.413 3.603-10.939 14.212-10.939 14.212"
					fill="#6ea843"
				/>
				<g fill="#a4cd49">
					<path
						d="m411.33 268.23c0 3.775-3.06 6.836-6.836 6.836-3.775 0-6.836-3.061-6.836-6.836s3.06-6.836 6.836-6.836c3.775 0 6.836 3.061 6.836 6.836z"
					/>
					<path
						d="m407.63 251.38c0 1.462-1.185 2.648-2.648 2.648-1.462 0-2.648-1.185-2.648-2.648 0-1.462 1.185-2.648 2.648-2.648 1.463 1e-3 2.648 1.186 2.648 2.648z"
					/>
					<circle cx="366.38" cy="285.2" r="5.673" />
					<path
						d="m322.66 276.55c0 1.646-1.335 2.981-2.981 2.981s-2.981-1.335-2.981-2.981 1.335-2.981 2.981-2.981 2.981 1.335 2.981 2.981z"
					/>
					<circle cx="293.91" cy="263.62" r="6.067" />
				</g>
				<g fill="#13304e">
					<circle cx="319.47" cy="370.78" r="12.207" opacity=".2" />
					<circle cx="304.21" cy="356.18" r="3.048" opacity=".2" />
					<circle cx="436.62" cy="337.34" r="3.048" opacity=".2" />
					<path
						d="m319.91 349.31c0 2.483-2.013 4.495-4.496 4.495s-4.495-2.013-4.495-4.495c0-2.483 2.013-4.496 4.495-4.496 2.483 0 4.496 2.013 4.496 4.496z"
						opacity=".2"
					/>
					<path
						d="m271.08 322.09c0 3.529-2.861 6.39-6.39 6.39s-6.39-2.861-6.39-6.39 2.861-6.39 6.39-6.39 6.39 2.861 6.39 6.39z"
						opacity=".2"
					/>
				</g>
				<g fill="#dbebb7">
					<path
						d="m288.01 170.19h69.303s-4.397-16.271-19.029-11.818c-3.343-21.531-32.318-23.299-34.93 1.322-11.296-2.633-15.344 10.496-15.344 10.496z"
					/>
					<path
						d="m374.82 145.76h81.442s-6.904-12.076-22.333-7.717c-0.514-16.214-24.209-27.035-41.659-9.659-13.886-5.011-22.557 9.934-17.45 17.376z"
					/>
					<path
						d="m403.34 101.09h-99.533s8.437-14.758 27.294-9.431c0.629-19.815 29.587-33.04 50.913-11.805 16.971-6.125 27.567 12.14 21.326 21.236z"
					/>
				</g>
				<g fill="#13304e">
					<path
						d="m419.74 213.34c-0.1 0-0.201-0.015-0.299-0.046-0.392-0.123-0.669-0.473-0.698-0.883-0.2-2.796-4.275-4.456-4.316-4.473-0.512-0.205-0.763-0.786-0.559-1.298 0.204-0.513 0.785-0.763 1.296-0.561 0.182 0.072 3.802 1.538 5.115 4.416 3.089-2.11 7.432-1.038 7.643-0.984 0.534 0.137 0.856 0.68 0.72 1.214-0.136 0.535-0.68 0.858-1.214 0.724-0.048-0.012-4.748-1.159-6.91 1.519-0.193 0.24-0.481 0.372-0.778 0.372z"
					/>
					<path
						d="m435.66 193.96c-0.023 0-0.046-1e-3 -0.069-2e-3 -0.41-0.028-0.761-0.304-0.885-0.696-0.544-1.718-3.472-2.182-3.501-2.186-0.547-0.078-0.927-0.585-0.849-1.131 0.078-0.547 0.588-0.93 1.131-0.849 0.137 0.02 2.743 0.412 4.254 2.07 1.907-1.837 4.966-1.815 5.126-1.814 0.552 8e-3 0.993 0.463 0.985 1.015s-0.478 1.018-1.015 0.985c-0.014 6e-3 -3.299-0.012-4.274 2.038-0.167 0.35-0.519 0.57-0.903 0.57z"
					/>
					<path
						d="m402.2 186.13c-0.348 0-0.676-0.182-0.858-0.488-1.436-2.409-5.821-2.063-5.866-2.057-0.545 0.043-1.034-0.359-1.082-0.909-0.048-0.549 0.357-1.034 0.907-1.083 0.195-0.017 4.087-0.334 6.554 1.648 1.812-3.274 6.173-4.267 6.385-4.313 0.538-0.116 1.07 0.223 1.189 0.762 0.119 0.538-0.222 1.072-0.76 1.192-0.048 0.011-4.762 1.098-5.491 4.462-0.087 0.401-0.411 0.709-0.816 0.775-0.054 6e-3 -0.108 0.011-0.162 0.011z"
					/>
				</g>
			</g>
			<g id="smoke" style:opacity={smoke.opacity}>
				<path
					d="m221.34 162.18s-2.999-3.097 0-7.976c-13.702 2.91-30.194-5.249-33.563-14.566-9.867 10.769-26.287 12.447-31.235-3.878-6.241 0-7.91-10.422-1.697-12.901 1.225-5.762 5.601-3.413 5.601-3.413s14.177-11.376 20.843 4.317c10.177-1.952 9.165 7.208 9.165 7.208s32.335-9.891 33.194 12.774c7.234-0.178 6.38 6.554 6.38 6.554s4.884 4.977-1.239 11.882"
					fill="#7b8c9d"
				/>
				<path
					d="m168.7 137.52c0.233 1.562-0.844 3.018-2.407 3.251-1.562 0.233-3.018-0.844-3.251-2.407-0.233-1.562 0.844-3.018 2.407-3.251 1.562-0.233 3.018 0.844 3.251 2.407z"
					fill="#919fad"
				/>
				<path
					d="m179.39 139.1c0.32 2.143-1.158 4.139-3.3 4.458-2.143 0.32-4.139-1.158-4.458-3.3-0.32-2.142 1.158-4.139 3.3-4.458 2.142-0.32 4.138 1.158 4.458 3.3z"
					fill="#919fad"
				/>
				<path
					d="m187.35 117.1s-6.112-3.222-3.082-11.429c-7.165 5.097-20.464-1.687-19.199-12.654-9.35 4.749-25.952 1.621-19.682-16.854-7.038-0.497-10.174-14.473 0.52-16.327-1.334-9.86 29.406-26.829 42.719 1.877 9.942-2.516 13.518 12.426 3.914 15.665 5.685 1.873 8.574 14.265 0.259 19.014 15.404-1.65 16.834 12.74 15.056 19.84"
					fill="#7b8c9d"
				/>
				<g fill="#919fad">
					<path
						d="m159.29 87.424c0.226 1.517-0.82 2.93-2.336 3.156-1.517 0.226-2.93-0.819-3.156-2.336s0.82-2.93 2.336-3.156c1.516-0.227 2.929 0.819 3.156 2.336z"
					/>
					<path
						d="m172.46 84.507c0.303 2.033-1.099 3.927-3.132 4.231-2.033 0.303-3.927-1.099-4.231-3.132-0.303-2.033 1.099-3.927 3.132-4.231 2.034-0.303 3.928 1.099 4.231 3.132z"
					/>
					<path
						d="m181.75 95.488c0.456 3.056-1.651 5.902-4.707 6.359s-5.902-1.651-6.359-4.707c-0.456-3.056 1.651-5.902 4.707-6.358 3.056-0.457 5.903 1.651 6.359 4.706z"
					/>
				</g>
				<path
					d="m71.691 95.01s12.473-1.01 15.96 10.47c3.524 11.602-6.383 20.801-6.383 20.801s3.193 0.415 2.659 3.866c4.285-1.399 8.959 1.771 8.085 6.632 7.752 2.84 8.499 13.57 0.663 17.557 10.002 9.101-1.815 22.788-1.815 22.788h-11.075s-1.546-7.502-3.006-10.384c-12.784 2.55-15.239-8.59-15.239-8.59s-11.102-0.998-10.16-13.786c-14.819 1.98-19.234-13.111-11.477-20.786-15.38-10.096-7.432-41.494 14.676-36.325 3.507-4.819 6.867-0.203 6.867-0.203s9.295-2.804 10.245 7.96z"
					fill="#7b8c9d" opacity={partialsmoke.opacity}
				/>
				<g fill="#919fad" opacity={partialsmoke.opacity} >
					<path
						d="m52.431 135.5c0.087 2.937-2.224 5.389-5.161 5.476s-5.389-2.224-5.476-5.161 2.224-5.389 5.161-5.476c2.938-0.087 5.39 2.223 5.476 5.161z"
					/>
					<path
						d="m60.553 146.27c0.041 1.398-1.059 2.565-2.457 2.607-1.398 0.041-2.565-1.059-2.607-2.457-0.041-1.398 1.059-2.565 2.457-2.607 1.399-0.041 2.566 1.059 2.607 2.457z"
					/>
					<path
						d="m92.133 159.57c0.041 1.398-1.059 2.565-2.457 2.607-1.398 0.041-2.565-1.059-2.607-2.457-0.041-1.398 1.059-2.565 2.457-2.607 1.399-0.041 2.566 1.059 2.607 2.457z"
					/>
					<path
						d="m66.666 137.69c0.071 2.387-1.807 4.378-4.193 4.449-2.387 0.071-4.378-1.807-4.449-4.193s1.807-4.378 4.193-4.449 4.378 1.806 4.449 4.193z"
					/>
				</g>
			</g>
			<g id="smokestack" transform="translate(0 {smokestack.y})">
				<rect x="221.34" y="164.75" width="7.448" height="87.95" fill="#38516a" />
				<rect x="219.24" y="160.41" width="11.635" height="8.672" fill="#13304e" />
				<rect x="221.34" y="174.17" width="7.448" height="5.469" fill="#13304e" />
				<g fill="#7b8c9d">
					<rect x="221.34" y="184.55" width="7.448" height="2.643" />
					<rect x="221.34" y="190.46" width="7.448" height="2.643" />
					<rect x="221.34" y="196.36" width="7.448" height="2.643" />
					<rect x="221.34" y="202.27" width="7.448" height="2.643" />
				</g>
				<rect x="184.26" y="117.98" width="23.371" height="147.6" fill="#13304e" />
				<g fill="#fff">
					<rect x="184.26" y="171.73" width="23.371" height="2.439" />
					<rect x="184.26" y="176.9" width="23.371" height="2.439" />
					<rect x="184.26" y="182.08" width="23.371" height="2.439" />
					<rect x="184.26" y="187.25" width="23.371" height="2.439" />
				</g>
				<g fill="#38516a">
					<path
						d="m206.25 113.87h-20.607c-2.118 0-3.835 1.717-3.835 3.835v0.536c0 2.118 1.717 3.835 3.835 3.835h20.607c2.118 0 3.835-1.717 3.835-3.835v-0.536c0-2.118-1.717-3.835-3.835-3.835z"
					/>
					<rect x="184.26" y="128.19" width="23.371" height="8.892" />
					<rect x="184.26" y="143.19" width="23.371" height="8.892" />
					<rect x="184.26" y="158.19" width="23.371" height="8.892" />
				</g>
				<path
					d="m250 51.712c-1.86 0-3.367 1.507-3.367 3.367v325.63h6.734v-325.63c0-1.859-1.507-3.367-3.367-3.367z"
					fill="#13304e"
				/>
				<g fill="#13304e">
					<polygon
						transform="translate(3.7586e-6)"
						points="68.938 377.45 68.938 186.09 176.39 195.1 176.39 377.45"
					/>
					<rect
						transform="translate(3.7586e-6)"
						x="78.4"
						y="174.17"
						width="15.663"
						height="33.613"
					/>
					<rect
						transform="translate(3.7586e-6)"
						x="101.51"
						y="179.64"
						width="4.668"
						height="19.257"
					/>
					<rect
						transform="translate(3.7586e-6)"
						x="112.77"
						y="167.74"
						width="9.893"
						height="33.613"
					/>
					<rect
						transform="translate(3.7586e-6)"
						x="65.465"
						y="200.39"
						width="52.791"
						height="16.71"
					/>
					<path
						d="m94.759 171.82h-17.055c-0.697 0-1.262 0.565-1.262 1.262v2.177c0 0.697 0.565 1.262 1.262 1.262h17.056c0.697 0 1.262-0.565 1.262-1.262v-2.177c0-0.696-0.565-1.262-1.263-1.262z"
					/>
				</g>
				<g fill="#38516a">
					<path
						d="m84.084 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.962 2.148-2.148 2.148z"
					/>
					<path
						d="m98.617 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.962 2.148-2.148 2.148z"
					/>
					<path
						d="m113.15 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.961 2.148-2.148 2.148z"
					/>
				</g>
			</g>
			<rect x="51.438" y="275.51" width="113.85" height="105.31" fill="#13304e" />
			<polygon points="51.438 264.7 51.438 275.51 165.29 275.51 165.29 226.5" fill="#38516a" />
			<g stroke-width="1.827">
				<rect x="58.614" y="283.81" width="16.063" height="25.925" fill="#38516a" />
				<rect x="61.836" y="288.5" width="9.619" height="16.532" fill="#fff" />
				<rect x="80.785" y="283.81" width="16.063" height="25.925" fill="#38516a" />
				<rect x="84.008" y="288.5" width="9.618" height="16.532" fill="#fff" />
				<rect x="102.96" y="283.81" width="16.063" height="25.925" fill="#38516a" />
				<rect x="106.18" y="288.5" width="9.619" height="16.532" fill="#fff" />
				<rect x="58.614" y="315.75" width="16.063" height="25.925" fill="#38516a" />
				<rect x="61.836" y="320.45" width="9.619" height="16.532" fill="#fff" />
				<rect x="80.785" y="315.75" width="16.063" height="25.925" fill="#38516a" />
				<rect x="84.008" y="320.45" width="9.618" height="16.532" fill="#fff" />
				<rect x="102.96" y="315.75" width="16.063" height="25.925" fill="#38516a" />
				<rect x="106.18" y="320.45" width="9.619" height="16.532" fill="#fff" />
			</g>
			<rect x="51.438" y="349.31" width="113.85" height="31.504" fill="#38516a" />
			<g fill="#13304e">
				<rect x="54.208" y="352.97" width="8.812" height="4.489" />
				<rect x="68.507" y="352.97" width="8.812" height="4.489" />
				<rect x="82.806" y="352.97" width="8.812" height="4.489" />
				<rect x="97.105" y="352.97" width="8.812" height="4.489" />
				<rect x="111.4" y="352.97" width="8.812" height="4.489" />
				<rect x="125.7" y="352.97" width="8.812" height="4.489" />
				<rect x="140" y="352.97" width="8.812" height="4.489" />
				<rect x="154.3" y="352.97" width="8.812" height="4.489" />
				<rect x="61.058" y="359.58" width="8.812" height="4.489" />
				<rect x="75.358" y="359.58" width="8.812" height="4.489" />
				<rect x="89.657" y="359.58" width="8.812" height="4.489" />
				<rect x="103.96" y="359.58" width="8.812" height="4.489" />
				<rect x="118.26" y="359.58" width="8.812" height="4.489" />
				<rect x="132.55" y="359.58" width="8.812" height="4.489" />
				<rect x="146.85" y="359.58" width="8.812" height="4.489" />
				<rect x="54.208" y="366.29" width="8.812" height="4.489" />
				<rect x="68.507" y="366.29" width="8.812" height="4.489" />
				<rect x="82.806" y="366.29" width="8.812" height="4.489" />
				<rect x="97.105" y="366.29" width="8.812" height="4.489" />
				<rect x="111.4" y="366.29" width="8.812" height="4.489" />
				<rect x="125.7" y="366.29" width="8.812" height="4.489" />
				<rect x="140" y="366.29" width="8.812" height="4.489" />
				<rect x="154.3" y="366.29" width="8.812" height="4.489" />
				<rect x="61.058" y="372.9" width="8.812" height="4.489" />
				<rect x="75.358" y="372.9" width="8.812" height="4.489" />
				<rect x="89.657" y="372.9" width="8.812" height="4.489" />
				<rect x="103.96" y="372.9" width="8.812" height="4.489" />
				<rect x="118.26" y="372.9" width="8.812" height="4.489" />
				<rect x="132.55" y="372.9" width="8.812" height="4.489" />
				<rect x="146.85" y="372.9" width="8.812" height="4.489" />
			</g>
			<rect x="133.37" y="275.51" width="113.85" height="105.31" fill="#38516a" />
			<polygon points="133.37 275.51 247.22 275.51 247.22 226.5 133.37 264.7" fill="#7b8c9d" />
			<g stroke-width="1.827">
				<rect x="140.55" y="283.81" width="16.063" height="25.925" fill="#13304e" />
				<rect x="143.77" y="288.5" width="9.618" height="16.532" fill="#fff" />
				<rect x="162.72" y="283.81" width="16.063" height="25.925" fill="#13304e" />
				<rect x="165.94" y="288.5" width="9.619" height="16.532" fill="#fff" />
				<rect x="184.89" y="283.81" width="16.063" height="25.925" fill="#13304e" />
				<rect x="188.11" y="288.5" width="9.618" height="16.532" fill="#fff" />
				<rect x="140.55" y="315.75" width="16.063" height="25.925" fill="#13304e" />
				<rect x="143.77" y="320.45" width="9.618" height="16.532" fill="#fff" />
				<rect x="162.72" y="315.75" width="16.063" height="25.925" fill="#13304e" />
				<rect x="165.94" y="320.45" width="9.619" height="16.532" fill="#fff" />
				<rect x="184.89" y="315.75" width="16.063" height="25.925" fill="#13304e" />
				<rect x="188.11" y="320.45" width="9.618" height="16.532" fill="#fff" />
			</g>
			<rect x="133.37" y="349.31" width="113.85" height="31.504" fill="#13304e" />
			<g opacity=".2">
				<g fill="#13304e" stroke-width="1.827">
					<rect x="136.14" y="352.97" width="8.812" height="4.489" />
					<rect x="150.44" y="352.97" width="8.812" height="4.489" />
					<rect x="164.74" y="352.97" width="8.812" height="4.489" />
					<rect x="179.04" y="352.97" width="8.812" height="4.489" />
					<rect x="193.34" y="352.97" width="8.812" height="4.489" />
					<rect x="207.64" y="352.97" width="8.812" height="4.489" />
					<rect x="221.94" y="352.97" width="8.812" height="4.489" />
					<rect x="236.24" y="352.97" width="8.812" height="4.489" />
					<rect x="142.99" y="359.58" width="8.812" height="4.489" />
					<rect x="157.29" y="359.58" width="8.812" height="4.489" />
					<rect x="171.59" y="359.58" width="8.812" height="4.489" />
					<rect x="185.89" y="359.58" width="8.812" height="4.489" />
					<rect x="200.19" y="359.58" width="8.812" height="4.489" />
					<rect x="214.49" y="359.58" width="8.812" height="4.489" />
					<rect x="228.79" y="359.58" width="8.812" height="4.489" />
					<rect x="136.14" y="366.29" width="8.812" height="4.489" />
					<rect x="150.44" y="366.29" width="8.812" height="4.489" />
					<rect x="164.74" y="366.29" width="8.812" height="4.489" />
					<rect x="179.04" y="366.29" width="8.812" height="4.489" />
					<rect x="193.34" y="366.29" width="8.812" height="4.489" />
					<rect x="207.64" y="366.29" width="8.812" height="4.489" />
					<rect x="221.94" y="366.29" width="8.812" height="4.489" />
					<rect x="236.24" y="366.29" width="8.812" height="4.489" />
					<rect x="142.99" y="372.9" width="8.812" height="4.489" />
					<rect x="157.29" y="372.9" width="8.812" height="4.489" />
					<rect x="171.59" y="372.9" width="8.812" height="4.489" />
					<rect x="185.89" y="372.9" width="8.812" height="4.489" />
					<rect x="200.19" y="372.9" width="8.812" height="4.489" />
					<rect x="214.49" y="372.9" width="8.812" height="4.489" />
					<rect x="228.79" y="372.9" width="8.812" height="4.489" />
				</g>
			</g>
			<g fill="#7b8c9d">
				<path
					d="m239.3 292.55h-28.954c-0.742 0-1.343-0.602-1.343-1.343 0-0.742 0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343s-0.602 1.343-1.343 1.343z"
				/>
				<path
					d="m239.3 303.03h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343 0 0.741-0.602 1.343-1.343 1.343z"
				/>
				<path
					d="m239.3 313.51h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343 0 0.741-0.602 1.343-1.343 1.343z"
				/>
				<path
					d="m239.3 323.99h-28.954c-0.742 0-1.343-0.602-1.343-1.343 0-0.742 0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343s-0.602 1.343-1.343 1.343z"
				/>
				<path
					d="m239.3 334.46h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.602 1.343 1.343s-0.602 1.343-1.343 1.343z"
				/>
			</g>
			<ellipse cx="250" cy="429.49" rx="141.42" ry="30.736" fill="#38516a" />
			<path
				d="m428.91 395.88h-357.81v33.548c0 5.848 4.741 10.589 10.589 10.589h336.64c5.848 0 10.589-4.741 10.589-10.589v-33.548z"
				fill="#13304e"
			/>
			<path
				d="m456.03 382.98h-412.07v20.443c0 5.848 4.741 10.589 10.589 10.589h390.89c5.848 0 10.589-4.741 10.589-10.589v-20.443z"
				fill="#a4cd49"
			/>
			<path
				d="m469.87 389.08h-439.75c-4.337 0-7.854-3.516-7.854-7.854 0-4.337 3.516-7.853 7.854-7.853h439.75c4.337 0 7.854 3.516 7.854 7.853 0 4.338-3.516 7.854-7.853 7.854z"
				fill="#6ea843"
			/>
		</g>
	</g>
	<g transform="matrix(.19988 0 0 .19988 -33.545 -13.576)">
		<g stroke-width="2.5016">
			<path
				d="m847.5 617.48c0 136.96-111.03 248-248 248-136.97 0-248-111.03-248-248 0-136.97 111.04-248 248-248 136.97 0 248 111.04 248 248z"
				fill="#c7b299"
			/>
			<g
				fill="none"
				stroke="#fff"
				stroke-dasharray="15.0093, 15.0093"
				stroke-miterlimit="10"
				stroke-width="5.0031"
			>
				<path
					d="m804.58 746.62h-399.25c-25.943 0-46.969-22.909-46.969-51.176v-2.325c0-28.26 21.026-51.169 46.969-51.169h290.36"
				/>
				<path d="m697.82 500.07c-34.2-0.375-66.379-0.375-99.495 0" />
				<path
					d="m620.96 500.07h126.49c35.168 0 63.67 31.054 63.67 69.367v3.151c0 38.31-28.502 69.365-63.67 69.365h-303.69"
				/>
			</g>
			<g stroke-width="2.5016">
				<rect x="679.79" y="528.64" width="101.59" height="1.88" />
				<rect x="679.79" y="522.63" width="66.835" height="1.878" />
				<rect x="342.79" y="452.64" width="101.59" height="1.879" />
				<rect x="342.79" y="446.62" width="66.835" height="1.878" />
				<rect x="625.77" y="856.37" width="3.388" height="3.653" />
				<rect x="617.76" y="856.37" width="3.389" height="3.653" />
				<rect x="609.74" y="856.37" width="3.388" height="3.653" />
				<rect x="601.73" y="856.37" width="3.386" height="3.653" />
				<rect x="593.72" y="856.37" width="3.385" height="3.653" />
				<rect x="585.71" y="856.37" width="3.387" height="3.653" />
				<rect x="577.69" y="856.37" width="3.387" height="3.653" />
				<rect x="569.68" y="856.37" width="3.386" height="3.653" />
				<rect x="561.67" y="856.37" width="3.387" height="3.653" />
				<rect x="553.66" y="856.37" width="3.385" height="3.653" />
				<rect x="545.64" y="856.37" width="3.385" height="3.653" />
				<rect x="537.63" y="856.37" width="3.383" height="3.653" />
				<rect x="529.62" y="856.37" width="3.386" height="3.653" />
				<rect x="746.36" y="816.23" width="3.388" height="3.654" />
				<rect x="738.35" y="816.23" width="3.389" height="3.654" />
				<rect x="730.33" y="816.23" width="3.388" height="3.654" />
				<rect x="722.32" y="816.23" width="3.386" height="3.654" />
				<rect x="714.31" y="816.23" width="3.386" height="3.654" />
				<rect x="706.3" y="816.23" width="3.386" height="3.654" />
				<rect x="698.28" y="816.23" width="3.389" height="3.654" />
				<rect x="690.27" y="816.23" width="3.386" height="3.654" />
				<rect x="682.26" y="816.23" width="3.389" height="3.654" />
				<rect x="674.24" y="816.23" width="3.386" height="3.654" />
				<rect x="666.23" y="816.23" width="3.386" height="3.654" />
				<rect x="658.22" y="816.23" width="3.383" height="3.654" />
				<rect x="650.21" y="816.23" width="3.386" height="3.654" />
				<rect x="844.31" y="696.42" width="2.995" height="3.478" />
				<rect x="837.22" y="696.42" width="2.993" height="3.478" />
				<rect x="830.14" y="696.42" width="2.994" height="3.478" />
				<rect x="823.05" y="696.42" width="2.997" height="3.478" />
				<rect x="815.96" y="696.42" width="2.994" height="3.478" />
				<rect x="808.87" y="696.42" width="2.995" height="3.478" />
				<rect x="801.78" y="696.42" width="2.998" height="3.478" />
				<rect x="794.7" y="696.42" width="2.993" height="3.478" />
				<rect x="787.61" y="696.42" width="2.994" height="3.478" />
				<rect x="780.52" y="696.42" width="2.998" height="3.478" />
				<rect x="773.44" y="696.42" width="2.994" height="3.478" />
				<rect x="766.35" y="696.42" width="2.991" height="3.478" />
				<rect x="759.26" y="696.42" width="2.995" height="3.478" />
				<rect x="647.43" y="431.48" width="3.887" height="4.514" />
				<rect x="638.23" y="431.48" width="3.882" height="4.514" />
				<rect x="629.04" y="431.48" width="3.885" height="4.514" />
				<rect x="619.85" y="431.48" width="3.887" height="4.514" />
				<rect x="610.66" y="431.48" width="3.883" height="4.514" />
				<rect x="601.46" y="431.48" width="3.886" height="4.514" />
				<rect x="592.27" y="431.48" width="3.888" height="4.514" />
				<rect x="583.08" y="431.48" width="3.883" height="4.514" />
				<rect x="573.88" y="431.48" width="3.884" height="4.514" />
				<rect x="564.69" y="431.48" width="3.889" height="4.514" />
				<rect x="555.5" y="431.48" width="3.883" height="4.514" />
				<rect x="546.31" y="431.48" width="3.88" height="4.514" />
				<rect x="537.11" y="431.48" width="3.885" height="4.514" />
				<rect x="760.47" y="483.7" width="3.885" height="4.515" />
				<rect x="751.28" y="483.7" width="3.881" height="4.515" />
				<rect x="742.09" y="483.7" width="3.884" height="4.515" />
				<rect x="732.89" y="483.7" width="3.888" height="4.515" />
				<rect x="723.7" y="483.7" width="3.884" height="4.515" />
				<rect x="714.5" y="483.7" width="3.886" height="4.515" />
				<rect x="705.31" y="483.7" width="3.888" height="4.515" />
				<rect x="696.12" y="483.7" width="3.882" height="4.515" />
				<rect x="686.92" y="483.7" width="3.885" height="4.515" />
				<rect x="677.73" y="483.7" width="3.89" height="4.515" />
				<rect x="668.54" y="483.7" width="3.883" height="4.515" />
				<rect x="659.35" y="483.7" width="3.88" height="4.515" />
				<rect x="650.15" y="483.7" width="3.885" height="4.515" />
				<rect x="919.85" y="675.04" width="3.886" height="4.516" />
				<rect x="910.66" y="675.04" width="3.882" height="4.516" />
				<rect x="901.47" y="675.04" width="3.885" height="4.516" />
				<rect x="892.28" y="675.04" width="3.887" height="4.516" />
				<rect x="883.09" y="675.04" width="3.882" height="4.516" />
				<rect x="873.89" y="675.04" width="3.885" height="4.516" />
				<rect x="864.7" y="675.04" width="3.888" height="4.516" />
				<rect x="855.5" y="675.04" width="3.883" height="4.516" />
				<rect x="846.31" y="675.04" width="3.885" height="4.516" />
				<rect x="837.11" y="675.04" width="3.889" height="4.516" />
				<rect x="827.93" y="675.04" width="3.883" height="4.516" />
				<rect x="818.73" y="675.04" width="3.88" height="4.516" />
				<rect x="809.54" y="675.04" width="3.886" height="4.516" />
				<path
					d="m564.25 831.64c0 0.186-0.011 0.341-0.03 0.467-0.022 0.129-0.05 0.228-0.09 0.307-0.041 0.076-0.086 0.131-0.14 0.167-0.054 0.029-0.109 0.046-0.169 0.046h-3.107v3.385c0 0.069-0.018 0.126-0.049 0.176-0.036 0.052-0.09 0.093-0.171 0.128-0.081 0.042-0.186 0.068-0.32 0.088-0.132 0.019-0.298 0.03-0.499 0.03-0.199 0-0.366-0.012-0.498-0.03-0.134-0.02-0.24-0.046-0.319-0.088-0.081-0.035-0.14-0.076-0.176-0.128-0.036-0.05-0.054-0.107-0.054-0.176v-3.385h-3.097c-0.058 0-0.113-0.017-0.164-0.046-0.05-0.036-0.096-0.091-0.134-0.167-0.041-0.079-0.074-0.178-0.096-0.307-0.024-0.126-0.036-0.281-0.036-0.467 0-0.18 0.011-0.336 0.03-0.467 0.019-0.13 0.048-0.233 0.083-0.31 0.038-0.073 0.081-0.131 0.127-0.164 0.045-0.032 0.099-0.049 0.158-0.049h3.127v-3.374c0-0.071 0.018-0.129 0.054-0.189 0.037-0.055 0.096-0.102 0.176-0.136 0.079-0.039 0.185-0.069 0.319-0.085 0.133-0.019 0.3-0.031 0.498-0.031 0.201 0 0.367 0.012 0.499 0.031 0.134 0.016 0.239 0.046 0.32 0.085 0.081 0.034 0.135 0.081 0.171 0.136 0.031 0.06 0.049 0.118 0.049 0.189v3.374h3.135c0.053 0 0.105 0.017 0.156 0.049 0.05 0.033 0.094 0.091 0.129 0.164 0.036 0.076 0.063 0.18 0.085 0.31 0.022 0.131 0.033 0.287 0.033 0.467z"
				/>
				<path
					d="m408.82 583.31c0 0.186-9e-3 0.341-0.028 0.467-0.022 0.128-0.052 0.227-0.093 0.306-0.039 0.078-0.085 0.131-0.138 0.167-0.053 0.031-0.111 0.047-0.169 0.047h-3.107v3.386c0 0.068-0.018 0.126-0.05 0.175-0.033 0.053-0.09 0.093-0.169 0.129-0.081 0.04-0.186 0.068-0.32 0.087-0.133 0.02-0.298 0.031-0.5 0.031-0.198 0-0.365-0.011-0.498-0.031-0.134-0.019-0.24-0.046-0.32-0.087-0.08-0.036-0.139-0.076-0.176-0.129-0.037-0.049-0.053-0.107-0.053-0.175v-3.386h-3.099c-0.058 0-0.112-0.016-0.163-0.047-0.05-0.035-0.095-0.089-0.133-0.167-0.042-0.079-0.074-0.177-0.096-0.306-0.024-0.126-0.036-0.281-0.036-0.467 0-0.181 0.011-0.336 0.032-0.467 0.018-0.129 0.046-0.232 0.082-0.308 0.038-0.074 0.079-0.132 0.125-0.165 0.047-0.033 0.101-0.049 0.16-0.049h3.127v-3.374c0-0.071 0.017-0.129 0.053-0.189 0.037-0.055 0.096-0.101 0.176-0.137 0.079-0.038 0.186-0.068 0.32-0.084 0.133-0.02 0.299-0.03 0.498-0.03 0.202 0 0.367 0.011 0.5 0.03 0.134 0.016 0.239 0.047 0.32 0.084 0.079 0.036 0.136 0.082 0.169 0.137 0.032 0.06 0.05 0.118 0.05 0.189v3.374h3.136c0.053 0 0.104 0.016 0.156 0.049 0.049 0.033 0.094 0.09 0.128 0.165 0.037 0.076 0.065 0.18 0.087 0.308 0.021 0.131 0.029 0.286 0.029 0.467z"
				/>
				<path
					d="m671.26 412.87c0 0.186-0.011 0.342-0.03 0.469-0.021 0.127-0.051 0.227-0.092 0.306-0.04 0.076-0.085 0.129-0.139 0.165-0.054 0.032-0.11 0.048-0.169 0.048h-3.106v3.385c0 0.069-0.019 0.127-0.051 0.176-0.033 0.05-0.091 0.093-0.17 0.128-0.08 0.039-0.186 0.068-0.319 0.087-0.132 0.019-0.298 0.03-0.5 0.03-0.198 0-0.365-0.011-0.497-0.03-0.135-0.02-0.241-0.048-0.32-0.087-0.08-0.036-0.139-0.078-0.176-0.128-0.037-0.049-0.054-0.107-0.054-0.176v-3.385h-3.099c-0.058 0-0.112-0.016-0.163-0.048-0.05-0.035-0.096-0.089-0.133-0.165-0.042-0.08-0.074-0.179-0.097-0.306-0.024-0.127-0.034-0.283-0.034-0.469 0-0.18 0.01-0.335 0.03-0.466 0.019-0.128 0.047-0.232 0.082-0.309 0.039-0.075 0.079-0.131 0.126-0.165 0.047-0.033 0.101-0.049 0.159-0.049h3.128v-3.375c0-0.069 0.017-0.129 0.054-0.187 0.037-0.057 0.096-0.103 0.176-0.137 0.079-0.039 0.186-0.069 0.32-0.086 0.132-0.019 0.299-0.03 0.497-0.03 0.202 0 0.368 0.011 0.5 0.03 0.134 0.018 0.239 0.047 0.319 0.086 0.079 0.034 0.137 0.08 0.17 0.137 0.032 0.058 0.051 0.117 0.051 0.187v3.375h3.135c0.054 0 0.104 0.016 0.156 0.049 0.049 0.034 0.095 0.09 0.128 0.165 0.037 0.077 0.066 0.18 0.087 0.309 0.02 0.131 0.031 0.286 0.031 0.466z"
				/>
				<path
					d="m503.85 398.5c0.295-0.292 0.587-0.581 0.885-0.866-0.185 0.179-0.429 0.419-0.885 0.866z"
					fill="#fff"
				/>
				<path
					d="m602.11 483.1 0.015-0.02c-9e-3 8e-3 -0.019 0.018-0.024 0.026l-2e-3 2e-3c2e-3 -1e-3 4e-3 -1e-3 0.011-8e-3z"
					fill="#fff"
				/>
				<rect x="265.35" y="673.16" width="117.43" height="2.178" />
				<rect x="265.35" y="666.2" width="77.251" height="2.175" />
				<path
					d="m460.22 804.28c1.441-4.596 3.755-8.968 6.98-12.835l-0.044 0.044-4.358-8.889 7.879-6.41 7.816 6.071-0.051 0.042c4.424-2.359 9.179-3.758 13.976-4.209l3.217-9.334 10.086 1.035 1.23 9.776c4.607 1.414 8.997 3.744 12.851 6.92l8.837-4.337 6.425 7.889-6.054 7.777c2.355 4.424 3.732 9.17 4.193 13.984l9.31 3.181-1.026 10.113-9.783 1.227c-1.411 4.61-3.731 8.998-6.928 12.857l4.323 8.828-7.879 6.406-7.755-6.031c-4.432 2.347-9.203 3.724-14.004 4.17l-3.207 9.342-10.101-1.037-1.221-9.813c-4.61-1.41-8.984-3.752-12.83-6.93l-8.863 4.351-6.417-7.884 6.067-7.796c-2.334-4.412-3.7-9.173-4.152-13.96l-9.353-3.206 1.027-10.105zm46.496 2.293c-4.837-5.943-13.56-6.826-19.501-1.992-5.944 4.837-6.841 13.545-2.007 19.491 4.832 5.943 13.567 6.851 19.505 2.022 5.944-4.834 6.846-13.58 2.003-19.521z"
					fill="#fff"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
				<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
					<path
						d="m514.28 835.07c-10.917 10.351-28.155 9.891-38.504-1.023-10.349-10.917-9.892-28.153 1.022-38.505"
					/>
					<path d="m520.16 826.96c-0.726 1.53-1.596 2.994-2.599 4.363" />
					<path
						d="m482.18 800.94c8.206-7.782 21.162-7.436 28.943 0.768 7.778 8.203 7.435 21.161-0.768 28.94"
					/>
					<path d="m477.76 807.03c0.543-1.15 1.201-2.249 1.954-3.275" />
				</g>
				<path
					d="m351.24 741.03c4.256-7.115 9.885-13.51 16.837-18.688l-0.09 0.057-3.729-16.633 15.762-7.566 10.65 13.299-0.101 0.047c8.351-2.17 16.874-2.609 25.085-1.437l9.132-14.338 16.471 5.781-1.865 16.863c7.149 4.216 13.562 9.877 18.738 16.739l16.538-3.716 7.588 15.788-13.252 10.589c2.17 8.351 2.568 16.849 1.407 25.096l14.309 9.061-5.774 16.518-16.87-1.872c-4.212 7.151-9.861 13.57-16.761 18.745l3.699 16.516-15.763 7.564-10.564-13.21c-8.361 2.151-16.902 2.545-25.119 1.364l-9.118 14.352-16.492-5.788 1.892-16.922c-7.152-4.211-13.534-9.884-18.699-16.745l-16.581 3.722-7.58-15.77 13.284-10.621c-2.134-8.32-2.516-16.839-1.35-25.035l-14.373-9.116 5.775-16.51zm76.925 22.491c-5.714-11.89-19.964-16.862-31.85-11.159-11.892 5.711-16.89 19.936-11.183 31.828 5.707 11.886 19.965 16.909 31.846 11.212 11.889-5.706 16.907-19.992 11.187-31.881z"
					fill="#fff"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
				<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
					<path
						d="m429.4 814.28c-22.43 12.949-51.103 5.262-64.05-17.161-12.948-22.426-5.264-51.099 17.161-64.048"
					/>
					<path d="m442.49 803.07c-1.827 2.271-3.872 4.368-6.099 6.257" />
					<path
						d="m389.35 744.25c16.859-9.733 38.411-3.958 48.145 12.896 9.732 16.856 3.958 38.408-12.896 48.145"
					/>
					<path d="m379.51 752.68c1.373-1.705 2.91-3.284 4.585-4.702" />
				</g>
				<g stroke-width="2.5016">
					<polygon
						points="592.65 470.22 614.11 470.22 603.14 497.88"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m603.14 499.32h-0.011c-0.599-4e-3 -1.132-0.375-1.345-0.934l-10.484-27.653c-0.167-0.445-0.106-0.944 0.164-1.336s0.716-0.625 1.191-0.625h21.456c0.478 0 0.926 0.238 1.196 0.635 0.268 0.397 0.325 0.902 0.147 1.347l-10.97 27.652c-0.218 0.552-0.752 0.914-1.344 0.914zm-8.389-27.652 8.419 22.202 8.807-22.202z"
					/>
					<polygon
						points="603.14 457.06 613.63 469.94 592.17 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m613.65 471.38h-0.021-21.456c-0.563 0-1.077-0.328-1.314-0.841-0.235-0.512-0.153-1.115 0.212-1.546l10.961-12.871c0.278-0.327 0.652-0.534 1.117-0.509 0.433 5e-3 0.837 0.2 1.106 0.533l10.359 12.706c0.298 0.265 0.484 0.65 0.484 1.079 2e-3 0.801-0.647 1.449-1.448 1.449zm-18.34-2.895h15.27l-7.468-9.162z"
					/>
					<polygon
						points="581.68 457.06 592.17 469.94 570.72 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m592.2 471.38h-0.025-21.456c-0.566 0-1.08-0.328-1.315-0.841-0.238-0.512-0.156-1.115 0.21-1.546l10.966-12.871c0.278-0.327 0.644-0.534 1.12-0.509 0.429 5e-3 0.833 0.2 1.104 0.533l10.359 12.706c0.296 0.265 0.484 0.65 0.484 1.079 1e-3 0.801-0.647 1.449-1.447 1.449zm-18.346-2.895h15.275l-7.468-9.162z"
					/>
					<polygon
						points="624.59 457.06 635.08 469.94 613.63 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m635.11 471.38h-0.021-21.456c-0.565 0-1.079-0.328-1.314-0.841-0.237-0.512-0.153-1.115 0.211-1.546l10.968-12.871c0.278-0.327 0.653-0.534 1.118-0.509 0.429 5e-3 0.833 0.2 1.106 0.534l10.354 12.706c0.297 0.265 0.483 0.65 0.483 1.079 0 0.8-0.648 1.448-1.449 1.448zm-18.343-2.895h15.274l-7.468-9.162z"
					/>
					<polygon
						points="592.17 469.94 581.68 457.06 603.14 457.06"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m592.17 471.38h-0.014c-0.429-4e-3 -0.836-0.2-1.107-0.532l-10.493-12.871c-0.352-0.434-0.423-1.031-0.186-1.535 0.24-0.506 0.748-0.828 1.309-0.828h21.453c0.563 0 1.076 0.328 1.315 0.841 0.237 0.512 0.153 1.116-0.214 1.545l-10.96 12.87c-0.275 0.325-0.677 0.51-1.103 0.51zm-7.444-12.87 7.468 9.161 7.804-9.161z"
					/>
					<polygon
						points="613.63 469.94 603.14 457.06 624.59 457.06"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m613.63 471.38h-0.017c-0.43-4e-3 -0.833-0.2-1.106-0.532l-10.493-12.871c-0.353-0.433-0.424-1.031-0.186-1.535 0.24-0.506 0.748-0.828 1.309-0.828h21.458c0.563 0 1.078 0.328 1.315 0.841 0.237 0.512 0.152 1.116-0.214 1.545l-10.966 12.87c-0.275 0.325-0.676 0.51-1.1 0.51zm-7.446-12.87 7.471 9.161 7.807-9.161z"
					/>
					<polygon
						points="571.2 470.22 592.65 470.22 603.14 497.88"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m603.14 499.32c-0.339 0-0.677-0.119-0.948-0.353l-31.94-27.652c-0.457-0.395-0.621-1.034-0.41-1.6 0.213-0.567 0.754-0.943 1.357-0.943h21.456c0.601 0 1.14 0.372 1.353 0.934l10.4 27.426c0.128 0.216 0.202 0.47 0.202 0.74 0 0.8-0.648 1.448-1.449 1.448h-0.021zm-28.058-27.652 24.672 21.358-8.099-21.358z"
					/>
					<polygon
						points="635.08 470.22 613.63 470.22 603.17 497.85"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/>
					<path
						d="m603.17 499.3c-0.29 0-0.579-0.086-0.828-0.261-0.543-0.379-0.76-1.08-0.524-1.7l10.46-27.628c0.213-0.563 0.754-0.935 1.356-0.935h21.456c0.603 0 1.144 0.376 1.354 0.943 0.211 0.566 0.05 1.204-0.407 1.6l-31.919 27.628c-0.27 0.234-0.609 0.353-0.948 0.353zm11.463-27.628-8.08 21.337 24.649-21.337z"
					/>
				</g>
				<polygon
					points="583.66 824.35 582.4 831.73 588 824.35 600.88 824.35 600.88 802.67 578.09 802.67 578.09 824.35"
					fill="#fff"
				/>
				<path
					d="m588.36 816.74c-0.313 0-0.611-0.129-0.827-0.355l-1.868-1.953c-0.432-0.456-0.413-1.175 0.041-1.609 0.456-0.432 1.174-0.419 1.607 0.035l0.979 1.029 3.302-4.023c0.397-0.483 1.113-0.558 1.599-0.159 0.487 0.399 0.556 1.115 0.158 1.602l-4.115 5.017c-0.206 0.254-0.512 0.404-0.833 0.412-0.016 4e-3 -0.031 4e-3 -0.043 4e-3z"
					stroke-width="2.5016"
				/>
				<polygon
					points="461.51 555.58 460.25 562.96 465.85 555.58 478.74 555.58 478.74 533.9 455.94 533.9 455.94 555.58"
					fill="#fff"
				/>
				<path
					d="m466.22 547.98c-0.313 0-0.611-0.131-0.827-0.355l-1.868-1.956c-0.431-0.455-0.413-1.174 0.041-1.608 0.456-0.432 1.173-0.417 1.607 0.037l0.979 1.028 3.302-4.022c0.397-0.487 1.113-0.558 1.598-0.158 0.488 0.395 0.556 1.114 0.159 1.598l-4.115 5.019c-0.206 0.251-0.513 0.402-0.833 0.412-0.016 5e-3 -0.031 5e-3 -0.043 5e-3z"
				/>
				<path
					d="m572.41 770.18-9.883 6.87c-0.314 0.043-0.609 0.21-0.806 0.491-0.159 0.229-0.219 0.491-0.202 0.751-0.017 0.257 0.044 0.522 0.202 0.752 0.197 0.281 0.492 0.447 0.806 0.489l9.883 6.872c0.539 0.371 1.273 0.237 1.643-0.295 0.368-0.536 0.24-1.272-0.295-1.64l-8.889-6.179 8.889-6.178c0.535-0.372 0.663-1.104 0.295-1.641-0.369-0.529-1.104-0.661-1.643-0.292z"
				/>
				<path
					d="m582.99 770.18-9.884 6.87c-0.314 0.043-0.612 0.21-0.806 0.491-0.162 0.229-0.221 0.491-0.205 0.751-0.016 0.257 0.044 0.522 0.205 0.752 0.194 0.281 0.492 0.447 0.806 0.489l9.884 6.872c0.536 0.371 1.268 0.237 1.64-0.295 0.372-0.536 0.241-1.272-0.292-1.64l-8.894-6.179 8.894-6.178c0.533-0.372 0.664-1.104 0.292-1.641-0.373-0.529-1.105-0.661-1.64-0.292z"
				/>
				<path
					d="m593.56 769.72-9.881 6.873c-0.317 0.04-0.612 0.21-0.806 0.488-0.161 0.229-0.222 0.492-0.205 0.752-0.017 0.26 0.044 0.522 0.205 0.751 0.194 0.282 0.489 0.449 0.806 0.492l9.881 6.87c0.538 0.371 1.273 0.239 1.643-0.296 0.371-0.533 0.24-1.268-0.296-1.64l-8.891-6.178 8.891-6.179c0.536-0.372 0.667-1.104 0.296-1.639-0.37-0.535-1.105-0.663-1.643-0.294z"
				/>
				<path
					d="m604.14 769.72-9.885 6.873c-0.314 0.04-0.609 0.21-0.803 0.488-0.159 0.229-0.221 0.492-0.203 0.752-0.019 0.26 0.043 0.522 0.203 0.751 0.194 0.282 0.489 0.449 0.803 0.492l9.885 6.87c0.536 0.371 1.271 0.239 1.644-0.296 0.368-0.533 0.237-1.268-0.299-1.64l-8.888-6.178 8.888-6.179c0.536-0.372 0.667-1.104 0.299-1.639-0.373-0.535-1.108-0.663-1.644-0.294z"
				/>
				<path
					d="m777.09 785.21-9.884 6.872c-0.314 0.041-0.609 0.21-0.807 0.489-0.158 0.229-0.218 0.494-0.202 0.751-0.016 0.261 0.044 0.522 0.202 0.752 0.197 0.281 0.493 0.447 0.807 0.489l9.884 6.872c0.538 0.371 1.273 0.24 1.642-0.295 0.369-0.533 0.241-1.268-0.294-1.637l-8.89-6.182 8.89-6.178c0.535-0.372 0.663-1.103 0.294-1.64-0.369-0.53-1.104-0.662-1.642-0.293z"
				/>
				<path
					d="m787.67 785.21-9.884 6.872c-0.313 0.041-0.611 0.21-0.805 0.489-0.162 0.229-0.222 0.494-0.206 0.751-0.016 0.261 0.044 0.522 0.206 0.752 0.193 0.281 0.491 0.447 0.805 0.489l9.884 6.872c0.536 0.371 1.269 0.24 1.64-0.295 0.372-0.533 0.241-1.268-0.292-1.637l-8.895-6.182 8.895-6.178c0.533-0.372 0.664-1.103 0.292-1.64-0.371-0.53-1.104-0.662-1.64-0.293z"
				/>
				<path
					d="m798.24 784.76-9.881 6.873c-0.316 0.044-0.612 0.21-0.807 0.488-0.16 0.229-0.221 0.494-0.205 0.755-0.016 0.257 0.045 0.518 0.205 0.751 0.194 0.278 0.49 0.446 0.807 0.489l9.881 6.87c0.538 0.374 1.273 0.239 1.643-0.292 0.372-0.536 0.24-1.271-0.295-1.643l-8.892-6.175 8.892-6.182c0.535-0.368 0.667-1.103 0.295-1.637-0.369-0.534-1.105-0.665-1.643-0.297z"
				/>
				<path
					d="m808.82 784.76-9.887 6.873c-0.313 0.044-0.609 0.21-0.804 0.488-0.158 0.229-0.221 0.494-0.201 0.755-0.019 0.257 0.043 0.518 0.201 0.751 0.194 0.278 0.49 0.446 0.804 0.489l9.887 6.87c0.535 0.374 1.271 0.239 1.642-0.292 0.369-0.536 0.238-1.271-0.297-1.643l-8.89-6.175 8.89-6.182c0.535-0.368 0.666-1.103 0.297-1.637-0.371-0.534-1.107-0.665-1.642-0.297z"
				/>
				<path
					d="m521.44 519.92-9.883 6.872c-0.314 0.042-0.609 0.21-0.806 0.489-0.159 0.229-0.219 0.495-0.203 0.753-0.016 0.259 0.044 0.52 0.203 0.751 0.197 0.28 0.492 0.449 0.806 0.489l9.883 6.871c0.539 0.373 1.273 0.24 1.642-0.295 0.369-0.533 0.241-1.268-0.295-1.637l-8.889-6.18 8.889-6.18c0.536-0.37 0.664-1.103 0.295-1.638-0.369-0.532-1.104-0.664-1.642-0.295z"
				/>
				<path
					d="m532.02 519.92-9.884 6.872c-0.315 0.042-0.612 0.21-0.806 0.489-0.161 0.229-0.222 0.495-0.205 0.753-0.017 0.259 0.044 0.52 0.205 0.751 0.194 0.28 0.492 0.449 0.806 0.489l9.884 6.871c0.535 0.373 1.268 0.24 1.639-0.295 0.372-0.533 0.24-1.268-0.292-1.637l-8.895-6.18 8.895-6.18c0.533-0.37 0.664-1.103 0.292-1.638-0.371-0.532-1.104-0.664-1.639-0.295z"
				/>
				<path
					d="m542.59 519.47-9.881 6.871c-0.317 0.044-0.612 0.211-0.806 0.489-0.162 0.231-0.222 0.494-0.205 0.754-0.017 0.257 0.044 0.521 0.205 0.751 0.194 0.28 0.489 0.445 0.806 0.489l9.881 6.871c0.538 0.373 1.273 0.239 1.642-0.294 0.372-0.535 0.241-1.27-0.295-1.64l-8.892-6.177 8.892-6.18c0.536-0.37 0.667-1.105 0.295-1.638-0.369-0.535-1.104-0.665-1.642-0.296z"
				/>
				<path
					d="m553.17 519.47-9.886 6.871c-0.314 0.044-0.609 0.211-0.803 0.489-0.159 0.231-0.222 0.494-0.202 0.754-0.019 0.257 0.043 0.521 0.202 0.751 0.194 0.28 0.489 0.445 0.803 0.489l9.886 6.871c0.536 0.373 1.271 0.239 1.642-0.294 0.369-0.535 0.238-1.27-0.298-1.64l-8.889-6.177 8.889-6.18c0.536-0.37 0.667-1.105 0.298-1.638-0.371-0.535-1.106-0.665-1.642-0.296z"
				/>
				<rect x="563.04" y="704.74" width="38.091" height="2.306" />
				<rect x="514.23" y="704.74" width="38.092" height="2.306" />
				<rect x="503.52" y="704.74" width="3.571" height="2.306" />
				<rect x="307.35" y="587.22" width="73.093" height="2.306" />
				<rect x="213.69" y="587.22" width="73.09" height="2.306" />
				<rect x="193.14" y="587.22" width="6.855" height="2.306" />
			</g>
			<path
				d="m811.81 738.74c0.759-1.984 1.177-4.137 1.177-6.386 0-9.913-8.032-17.944-17.947-17.944-8.04 0-14.843 5.287-17.121 12.58-2.123-2.992-5.613-4.946-9.562-4.946-6.473 0-11.717 5.247-11.717 11.715 0 1.691 0.362 3.298 1.009 4.752h-6.552c-4.421 0-8.008 3.582-8.008 8.01 0 4.415 3.587 8.003 8.008 8.003h58.806c4.422 0 8.005-3.588 8.005-8.003-1e-3 -3.766-2.597-6.923-6.098-7.781z"
				fill="#f69823"
			/>
		</g>
		<path
			d="m775.66 747.82c-0.624-1.631-0.968-3.399-0.968-5.249 0-8.151 6.604-14.753 14.756-14.753 6.609 0 12.204 4.347 14.075 10.343 1.746-2.46 4.615-4.066 7.861-4.066 5.32 0 9.633 4.312 9.633 9.63 0 1.391-0.298 2.71-0.829 3.907h5.387c3.634 0 6.583 2.946 6.583 6.583 0 3.631-2.949 6.582-6.583 6.582h-48.347c-3.634 0-6.58-2.951-6.58-6.582 0-3.094 2.134-5.69 5.012-6.395z"
			fill="#fff"
			stroke="#000"
			stroke-miterlimit="10"
			stroke-width="7.5046"
		/>
		<g stroke-width="2.5016">
			<path
				d="m283.82 614.78-1.765-6e-3c-1.35-0.013-2.463 1.554-2.481 3.502l-0.043 4.979c-0.016 1.95 1.068 3.541 2.423 3.557l1.866 7e-3z"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="5.0031"
			/>
			<g stroke-width="2.5016">
				<g stroke="#000" stroke-width="5.0031">
					<polygon
						points="379.34 626.9 391.73 620.93 379.34 614.7"
						fill="none"
						stroke-linecap="round"
					/>
					<polygon
						points="391.73 620.97 388.47 619.26 388.44 622.62"
						fill="#231f20"
						stroke-miterlimit="10"
					/>
					<rect
						x="293.26"
						y="614.18"
						width="84.981"
						height="13.242"
						fill="#f59121"
						stroke-linecap="round"
					/>
				</g>
				<rect x="293.83" y="620.21" width="84.7" height="1.182" stroke-width="2.5016" />
				<rect x="285.9" y="613.45" width="5.122" height="14.697" fill="#fff" />
				<path
					d="m628.61 396.42c0-6.367 0.113-9.46 0.113-12.828h-12.2c2.523 5.95-1.082 8.911-3.993 8.911-2.707 0-6.212-2.961-3.688-8.911h-12.199c0 3.368 0.111 6.461 0.111 12.828-11.194-7.039-12.323 13.361 0 6.979 0 5.354 0.137 5.953 0.137 12.83h31.584c0-6.877 0.136-7.475 0.136-12.83 12.323 6.382 11.196-14.018-1e-3 -6.979z"
					clip-rule="evenodd"
					fill="#fff"
					fill-rule="evenodd"
					stroke-width="2.5016"
				/>
				<path
					d="m614.88 377.26c0.134 0.051 0.261 0.09 0.398 0.147l-0.033-12.479c-0.094 0-12.975 0.056-13.15 0.056 7.233-11.507-13.73-12.665-7.172 0-0.181 0-13.272-0.056-13.272-0.056 0 1.118 0.088 12.612 0.088 12.612-11.001-6.421-12.082 13.417 0 7.586v13.229h33.54v-13.053c-0.138 0.057-0.265 0.095-0.4 0.147-5.842 2.262-8.758-1.327-8.758-4.253-1e-3 -2.719 2.915-6.205 8.759-3.936z"
					fill="#fff"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="6.2539"
				/>
				<polygon points="642.46 397.74 655.03 398.27 641.93 385.17" stroke-width="2.5016" />
				<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
					<path
						d="m597.85 342.91c14.124-13.397 36.43-12.802 49.824 1.321 13.393 14.123 12.799 36.431-1.322 49.823"
					/>
					<path d="m590.24 353.39c0.938-1.98 2.066-3.872 3.364-5.644" />
				</g>
				<rect
					x="687.07"
					y="450.16"
					width="83.272"
					height="2.738"
					fill="#231f20"
					stroke-width="2.5016"
				/>
				<rect
					x="715.56"
					y="458.92"
					width="54.785"
					height="2.735"
					fill="#231f20"
					stroke-width="2.5016"
				/>
				<path
					d="m785.51 377.29c-35.702 0-66.191 17.513-78.268 42.179 12.076 24.671 42.565 42.188 78.268 42.188s66.19-17.517 78.267-42.188c-12.078-24.666-42.564-42.179-78.267-42.179z"
					fill="#fff"
					stroke-width="2.5016"
				/>
				<g stroke="#000" stroke-width="7.5046">
					<path
						d="m745.87 419.47c0-21.886 17.746-39.637 39.637-39.637 21.896 0 39.64 17.751 39.64 39.637 0 21.894-17.744 39.641-39.64 39.641-21.888 0-39.637-17.748-39.637-39.641z"
						fill="#fff"
					/>
					<path
						d="m785.51 377.29c-35.702 0-66.191 17.513-78.268 42.179 12.076 24.671 42.565 42.188 78.268 42.188s66.19-17.517 78.267-42.188c-12.078-24.666-42.564-42.179-78.267-42.179z"
						fill="none"
						stroke-miterlimit="10"
					/>
					<path
						d="m824.15 384.75c-10.824-3.361-21.527-5.957-34.021-5.386-35.665 1.624-66.454 21.745-77.395 46.934"
						fill="none"
						stroke-miterlimit="10"
					/>
				</g>
				<path
					d="m796.67 400.55-11.166 18.919v-21.969c-12.131 0-21.972 9.838-21.972 21.969 0 12.138 9.841 21.973 21.972 21.973 12.135 0 21.975-9.835 21.975-21.973-1e-3 -8.058-4.346-15.097-10.809-18.919z"
					fill="#f59121"
					stroke-width="2.5016"
				/>
				<path
					d="m799.51 443.72c-13.393 7.734-30.518 3.148-38.251-10.25-7.731-13.39-3.143-30.516 10.253-38.253"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
				<path
					d="m807.33 437.02c-1.095 1.363-2.313 2.621-3.644 3.741"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
				<path
					d="m794.93 419.48c0 0.257-0.014 0.473-0.041 0.648-0.03 0.178-0.07 0.317-0.126 0.425-0.057 0.107-0.117 0.182-0.192 0.23-0.075 0.042-0.151 0.068-0.235 0.068h-4.302v4.688c0 0.093-0.024 0.174-0.071 0.242-0.046 0.069-0.123 0.13-0.234 0.179-0.112 0.054-0.257 0.093-0.442 0.122-0.184 0.024-0.413 0.04-0.692 0.04-0.276 0-0.506-0.016-0.691-0.04-0.183-0.028-0.33-0.068-0.44-0.122-0.11-0.049-0.193-0.109-0.245-0.179-0.049-0.068-0.072-0.149-0.072-0.242v-4.688h-4.291c-0.079 0-0.156-0.026-0.225-0.068-0.071-0.048-0.134-0.122-0.187-0.23-0.057-0.108-0.103-0.248-0.133-0.425-0.036-0.175-0.049-0.391-0.049-0.648 0-0.251 0.013-0.461 0.041-0.645 0.026-0.179 0.067-0.321 0.115-0.426 0.054-0.106 0.11-0.183 0.176-0.231 0.063-0.045 0.138-0.067 0.222-0.067h4.33v-4.675c0-0.096 0.024-0.178 0.072-0.259 0.052-0.075 0.135-0.141 0.245-0.189 0.11-0.055 0.258-0.094 0.44-0.12 0.186-0.025 0.415-0.04 0.691-0.04 0.279 0 0.509 0.015 0.692 0.04 0.186 0.026 0.33 0.065 0.442 0.12 0.111 0.048 0.189 0.114 0.234 0.189 0.047 0.082 0.071 0.164 0.071 0.259v4.675h4.342c0.074 0 0.146 0.022 0.217 0.067 0.067 0.048 0.131 0.125 0.179 0.231 0.051 0.105 0.088 0.248 0.118 0.426 0.027 0.184 0.041 0.394 0.041 0.645z"
					stroke-width="2.5016"
				/>
			</g>
			<path
				d="m549.33 450.01c0 28.15-22.819 50.962-50.954 50.962-28.153 0-50.962-22.812-50.962-50.962 0-28.119 22.809-50.938 50.962-50.938 28.134 1e-3 50.954 22.82 50.954 50.938z"
				fill="#f69823"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/>
			<g stroke-width="2.5016">
				<path
					d="m538.21 450.01c0 22.011-17.832 39.834-39.834 39.834-21.986 0-39.816-17.823-39.816-39.834 0-21.974 17.829-39.8 39.816-39.8 22.002 1e-3 39.834 17.826 39.834 39.8z"
					fill="#fff"
				/>
				<path
					d="m525.89 450.01c0 15.22-12.31 27.531-27.514 27.531s-27.525-12.311-27.525-27.531c0-15.171 12.321-27.507 27.525-27.507s27.514 12.336 27.514 27.507z"
					fill="#f69823"
				/>
				<path
					d="m512.11 450.01c0 7.588-6.154 13.741-13.734 13.741s-13.72-6.152-13.72-13.741c0-7.562 6.14-13.706 13.72-13.706s13.734 6.144 13.734 13.706z"
					fill="#fff"
				/>
				<g
					fill="#c7b299"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				>
					<polygon points="523.06 414.38 536.88 400.54 538.73 409.66 524.89 423.51" />
					<polygon points="534.45 425.04 548.27 411.21 539.15 409.36 525.32 423.19" />
				</g>
				<path
					d="m499.86 450.82c-0.707 0.726-1.863 0.726-2.585 0-0.724-0.719-0.724-1.874 0-2.588l47.344-47.355c0.724-0.71 1.893-0.71 2.601 0 0.722 0.711 0.722 1.878 0 2.602z"
					stroke-width="2.5016"
				/>
			</g>
			<line
				x1="820.46"
				x2="835.93"
				y1="583.22"
				y2="583.22"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/>
			<path
				d="m786.05 546.22c20.435 0.738 36.4 17.901 35.663 38.336-0.736 20.435-17.902 36.401-38.338 35.662-20.431-0.738-36.401-17.9-35.659-38.334 0.736-20.439 17.901-36.402 38.334-35.664z"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/>
			<g stroke-width="2.5016">
				<g stroke-width="2.5016">
					<path
						d="m784.24 611.61c15.678 0.255 28.601-12.243 28.856-27.919 0.257-15.674-12.247-28.594-27.925-28.848-15.678-0.259-28.591 12.242-28.845 27.919-0.254 15.676 12.24 28.593 27.914 28.848z"
						fill="#fff"
						stroke-width="2.5016"
					/>
				</g>
				<path
					d="m811.27 586.47c0.291-1.638 0.437-3.302 0.437-4.967"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
				<path
					d="m774.05 607.87c15.1 5.498 32.202-3.251 36.587-18.688"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/>
			</g>
			<path
				d="m902.23 569.08h-55.653c-6.188 0-11.201 5.014-11.201 11.199v5.897c0 6.185 5.013 11.197 11.201 11.197h55.653z"
				fill="#f69823"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/>
			<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
				<line x1="857.32" x2="893.96" y1="576.06" y2="576.06" />
				<path d="m845.53 576.06h5.414" />
			</g>
			<rect
				x="906.84"
				y="569.45"
				width="8.846"
				height="27.537"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/>
			<rect
				x="337.13"
				y="501.06"
				width="104.92"
				height="65.891"
				fill="#f69823"
				stroke-width="2.5016"
			/>
			<path
				d="m439.95 503.16v61.693h-100.72v-61.693h100.72m4.197-4.197h-109.12v70.087h109.12v-65.89z"
				stroke-width="2.5016"
			/>
			<path
				d="m413.48 552.31c16.802 0 21.602 4.8 21.602 4.8v-60.013s-4.8-4.798-21.602-4.798c-16.805 0-24.01 9.601-24.01 9.601v60.013s7.205-9.603 24.01-9.603z"
				fill="#fff"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="6.2539"
			/>
			<path
				d="m389.71 561.91v-60.013s-7.206-9.601-24.007-9.601c-16.804 0-21.603 4.798-21.603 4.798v60.013s4.8-4.8 21.603-4.8c16.801 0 24.007 9.603 24.007 9.603z"
				fill="#fff"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="6.2539"
			/>
			<clipPath>
				<use xlink:href="#SVGID_1_" />
			</clipPath>
			<g
				clip-path="url(#SVGID_00000045615448653943012690000000638754117711156656_)"
				stroke-width="2.5016"
			>
				<g stroke-width="2.5016">
					<path
						d="m688.7 881.9v-155.55c0.451 0.014 0.894 0.044 1.345 0.044 23.849 0 43.752-16.767 48.641-39.149h1.175l1.259-0.921c12.165-8.864 19.445-23.137 19.445-38.163 0-26.019-21.177-47.193-47.213-47.193-0.498 0-1.002 6e-3 -1.505 0.031-0.916-25.237-21.739-45.461-47.152-45.461-6.153 0-12.291 1.225-17.98 3.562-11.333-15.511-29.171-24.661-48.561-24.661-21.97 0-41.94 11.897-52.51 30.77-5.96-4.179-13.042-6.425-20.47-6.425-19.757 0-35.818 16.064-35.818 35.809 0 1.055 0.047 2.098 0.157 3.159-25.309 0.823-45.377 21.663-45.64 47.176-0.314 30.368 15.799 42.861 56.954 42.058 50.809 0 101.37 0.26 101.37 0.26 8.724 11.3 22.358 18.608 37.735 18.608 0.608 0 1.197-0.067 1.8-0.093v176.14"
						fill="#f69823"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/>
					<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
						<path
							d="m569.66 587.46s-13.941 2.215-20.472 9.396c-6.458 7.121-5.511 19.208-5.511 19.208"
						/>
						<path
							d="m553.16 593.22s-5.883-10.283-7.369-19.048c-1.55-9.136 5.259-17.109 5.259-17.109"
						/>
						<path
							d="m519.75 597.05s-10.553 2.367-15.196 8.173c-4.592 5.757-3.288 14.952-3.288 14.952"
						/>
						<path
							d="m500.72 612.73s-11.28-10.673-10.852-19.552c0.421-8.752 3.913-15.882 3.913-15.882"
						/>
					</g>
					<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
						<path
							d="m561.36 648.38s-5.917-16.065-26.362-8.162c-13.201 5.097-11.685 19.147-11.685 19.147"
						/>
						<path
							d="m619.73 648.21s-20.71-0.091-20.406 26.42c0.194 17.117 14.681 23.44 14.681 23.44"
						/>
						<path
							d="m743.88 612.26s-18.646-19.514-48.068-5.136c-22.383 10.938-15.17 36.461-15.17 36.461"
						/>
					</g>
					<path
						d="m659.62 555.87s-4.698-0.377-18.879 6.761c-20.475 10.303-27.271 37.526-27.271 37.526"
						fill="none"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/>
					<path
						d="m595.28 606.6s11.79-8.703 20.618-7.632c8.694 1.06 17.562 10.236 17.562 10.236"
						fill="none"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/>
					<g fill="#fff" stroke-width="2.5016">
						<path
							d="m572.9 567.04c-1.028-1.004-1.104-2.634-0.155-3.729 6.943-8.008 15.308-12.513 24.175-13.017 8.903-0.51 17.718 2.969 25.479 10.096 1.104 1.03 1.171 2.726 0.16 3.833-1.019 1.107-2.739 1.193-3.843 0.171-6.665-6.096-14.077-9.093-21.486-8.66-7.369 0.419-14.416 4.277-20.372 11.136-0.979 1.146-2.702 1.266-3.836 0.276-0.047-0.034-0.08-0.063-0.122-0.106z"
						/>
						<path
							d="m724.68 618.81c0.982-1.053 2.609-1.164 3.724-0.238 8.162 6.764 12.851 15.029 13.553 23.881 0.707 8.891-2.572 17.779-9.527 25.696-1.002 1.128-2.699 1.234-3.829 0.249-1.129-0.998-1.254-2.714-0.255-3.84 5.944-6.802 8.773-14.277 8.178-21.675-0.583-7.355-4.598-14.315-11.587-20.119-1.167-0.957-1.325-2.673-0.362-3.828 0.036-0.046 0.064-0.084 0.105-0.126z"
						/>
					</g>
					<path
						d="m483.64 663c-0.727 0.773-1.925 0.857-2.748 0.175-6.02-4.989-9.479-11.087-9.999-17.616-0.519-6.556 1.899-13.117 7.03-18.957 0.74-0.831 1.99-0.907 2.824-0.182 0.833 0.737 0.923 2.001 0.188 2.831-4.385 5.016-6.473 10.533-6.035 15.99 0.431 5.43 3.395 10.558 8.552 14.84 0.859 0.708 0.976 1.974 0.264 2.825-0.024 0.036-0.047 0.061-0.076 0.094z"
						fill="#fff"
						stroke-width="2.5016"
					/>
					<g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046">
						<path d="m643.31 575.01c17.319-16.419 46.865-8.765 53.933 14.083" />
						<path d="m636.22 584.77c0.875-1.843 1.924-3.605 3.133-5.252" />
						<path d="m463.44 666.58c-16.42-17.319-8.765-46.866 14.086-53.933" />
						<path d="m473.21 673.67c-1.842-0.874-3.605-1.924-5.252-3.131" />
					</g>
				</g>
			</g>
		</g>
	</g>
  <g
     id="g17466"
     transform="matrix(1.0353729,0,0,1.0353729,144.55592,-101.20258)"
     style="display:inline;stroke-width:3.33464"
     opacity={impact.opacity}
     >
    <path
       sodipodi:type="star"
       style="fill:#fce94f;stroke-width:2.00955;stroke-miterlimit:2;stop-color:#000000"
       id="path17457"
       inkscape:flatsided="false"
       sodipodi:sides="32"
       sodipodi:cx="57.763123"
       sodipodi:cy="93.080566"
       sodipodi:r1="38.256306"
       sodipodi:r2="51.697708"
       sodipodi:arg1="0.38015018"
       sodipodi:arg2="0.47832495"
       inkscape:rounded="0"
       inkscape:randomized="0"
       d="m 93.288269,107.27595 10.370381,9.6007 -13.822368,-2.94285 8.298114,11.43939 -12.982655,-5.58292 5.906955,12.83847 -11.644025,-8.00843 3.288795,13.74416 -9.857922,-10.12618 0.544248,14.12169 -7.692984,-11.8548 -2.221214,13.95652 -5.232409,-13.12784 -4.901316,13.25501 -2.570756,-13.89638 -7.393063,12.04412 0.18969,-14.1309 -9.600699,10.37039 2.942847,-13.82237 -11.439385,8.29811 5.582911,-12.98266 -12.838462,5.90696 8.008428,-11.64403 -13.744165,3.2888 10.126184,-9.85792 L 8.4837127,108.70724 20.338511,101.01425 6.3819908,98.793038 19.509829,93.560628 6.254817,88.659313 20.1512,86.088557 8.1070785,78.695494 22.237976,78.885184 11.867594,69.284485 25.689963,72.227332 17.391849,60.787947 30.374504,66.370858 24.467549,53.532396 36.111574,61.540823 32.82278,47.796659 l 9.857921,10.126184 -0.544248,-14.121686 7.692984,11.854798 2.221214,-13.95652 5.23241,13.127838 4.901315,-13.255012 2.570756,13.896383 7.393063,-12.044122 -0.18969,14.130898 9.600699,-10.370382 -2.942847,13.822369 11.439385,-8.298114 -5.582911,12.982655 12.838462,-5.906955 -8.008427,11.644025 13.744164,-3.288795 -10.126184,9.857922 14.121684,-0.544248 -11.854796,7.692984 13.956516,2.221214 -13.127834,5.232409 13.255014,4.901316 -13.896385,2.57076 12.044125,7.39306 z"
       inkscape:transform-center-x="-3.6952773"
       inkscape:transform-center-y="-9.5914757"
       transform="translate(44.942165,6.4067277)" />
    <text
       xml:space="preserve"
       style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:{23.5*impact.scale}px;line-height:1.25;font-family:'Futura Md Bt';-inkscape-font-specification:'Futura Md Bt, Normal';font-variant-ligatures:normal;font-variant-caps:normal;font-variant-numeric:normal;font-feature-settings:normal;text-align:start;letter-spacing:0px;word-spacing:0px;writing-mode:lr-tb;text-anchor:start;fill:#000000;fill-opacity:1;stroke:none;stroke-width:0.482917"
       x="101.73655"
       y="108.82299"
       id="text17461"><tspan
         sodipodi:role="line"
         id="tspan17459"
         style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-family:Impact;-inkscape-font-specification:Impact;text-align:center;text-anchor:middle;stroke-width:0.482917"
         x="101.73655"
         y="108.82299">IMPACT</tspan></text>
  </g>
</svg>
