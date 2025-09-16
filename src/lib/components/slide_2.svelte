<script lang="ts">
	import { tween, all } from '@animotion/motion'
	const arrowToInvestor = tween({ opacity: 0, width: 0 }, { duration: 500 })
	const arrowToPolluter = tween({ opacity: 0, width: 0 , bold: 0}, { duration: 500 })
	const polluter = tween({ y: -500, opacity: 0 }, { duration: 500 })
	const impact = tween({ opacity: 0, scale: 1, text: 'IMPACT' }, { duration: 500 })
	const investor = tween({ opacity: 0, y: -500 }, { duration: 500 })
	const smoke = tween({ opacity: 1 }, { duration: 500 })
	const smokestack = tween({ y: 0 }, { duration: 500 })
	const noThanks = tween({ opacity: 0 }, { duration: 500 })
	const cannotMeasure = tween({ opacity: 0 }, { duration: 500 })
	export async function animate(stepNo: number) {
		if (stepNo == 0) {
			// hide arrow
			await arrowToInvestor.to({ opacity: 0 })
			// hide arrow
			await arrowToPolluter.to({ opacity: 0, bold: 0 })
			// show polluter
			await polluter.to({ y: 0, opacity: 1 })
			// Hide impact
			await impact.to({ opacity: 0, text: 'IMPACT' })
			// Hide investor
			await investor.to({ opacity: 0, y: -500 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// show smokestack
			await smokestack.to({ y: 0 })
			// Hide no thanks
			await noThanks.to({ opacity: 0 })
			// Hide cannot measure
			await cannotMeasure.to({ opacity: 0 })
		}
		if (stepNo == 1) {
			// Show investor
			await investor.to({ opacity: 1, y: 0 })
			// Hide impact
			await impact.to({ opacity: 0, text: 'IMPACT' })
			// Hide cannot measure
			await cannotMeasure.to({ opacity: 0 })
		}
		if (stepNo == 2) {
			// show arrow to investor
			await arrowToInvestor.to({ opacity: 1 })
			// show arrow to polluter
			await arrowToPolluter.to({ opacity: 1, bold: 0 })
			// Hide impact
			await impact.to({ opacity: 0, text: 'IMPACT' })
			// Hide cannot measure
		}
		if (stepNo == 3) {
			// hide smoke
			await smoke.to({ opacity: 0 })
			// hide smokestack
			await smokestack.to({ y: -1500 })
			// show impact
			await impact.to({ opacity: 1, text: 'IMPACT' })
			// Hide cannot measure
			await cannotMeasure.to({ opacity: 0 })
		}
		if (stepNo == 4) {
			// hide impact
			await impact.to({ opacity: 0, text: 'IMPACT' })
			// show smokestack
			await smokestack.to({ y: 0 })
			// show smoke
			await smoke.to({ opacity: 1 })
			// show no thanks
			await noThanks.to({ opacity: 1 }, { delay: 1000})
			// Hide cannot measure
			await cannotMeasure.to({ opacity: 0 })
		}
		if (stepNo == 5) {
			// show impact
			await impact.to({ opacity: 1, text: 'IMPACT?' })
			// bold message from investor
			await arrowToPolluter.to({ bold: 1 })
			// Hide cannot measure
			await cannotMeasure.to({ opacity: 0 })
		}
		if (stepNo == 6) {
			// show impact
			await impact.to({ opacity: 1, text: 'IMPACT?' })
			// bold message from investor
			await arrowToPolluter.to({ bold: 1 })
			// Show cannot measure
			await cannotMeasure.to({ opacity: 1 })
		}
	}
</script>

<svg
	width="1012.7"
	height="378.85"
	version="1.1"
	viewBox="0 0 506.36 189.43"
	xml:space="preserve"
	xmlns="http://www.w3.org/2000/svg"
	xmlns:xlink="http://www.w3.org/1999/xlink"
	overflow="visible"
>
	<!-- svg-source:excalidraw --><defs
		><style class="style-fonts">
			@font-face {
				font-family: Excalifont;
				src: url(data:font/woff2;base64,d09GMgABAAAAAAnMAA4AAAAAEGwAAAl3AAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGhYbgkAcNAZgAIEEEQgKlHiPUQsgAAE2AiQDPAQgBYMYByAbtAxRlJBWCdnPhGzOYR2zEYlsK1KBmhOk86L+6Of5m3/uQy9qbpBrIKrBTf60+7JH8P3a9r87xJJYqITCdIbu0aUkQq2gClfyk/Ce+dysJ+86OP1/GCIrTnImipxUW3XQQjsSiBiSZMVOVAbG//7e1H22Wup4F9wOtuMrUuqZu71RKT2lcjBi0VioAn1LOkJAJSHIAjsjturCAqwFCACbgQCDwJWB+M9hchOCGEclZIDhobOpFgwvTWU1YPgsbakHQwQA2DY2HmVN9UAHHwoEDIh33GhNpPH7cAAorOj5mx7jxWBt4Lx5FkWXq58Gthx4W2Zg0+PyzYx4pu6KApe0SRQGJrG7gnEANMOAU8QMZjSiGkkME0ATSE7W23USDx6GTBl4u8/zejYy0CQg0WMMlgMA8beboDV4+A1gjdwbMY9OgkOg0Jq1/R8DpDGG2hQAC0PRL5u+Ah1UEGKekCwg6LjJ8eHoFKKlyFBKo0wtnSatFTuKFNRo4LX8nAOP7LViUaCjrabC54WADvqDEOF1+rYQ4F8AohJ8kWjiRcx1yl75N4kWZnZg9NousKcELk/mhjau23PvUt004sP6MGPG+/Roaq7wa9ykknounMstnn5/cSq4HzwOnqPvgOmt5MwDvo/zPElT2PcLdRU/CkMZS5jL9JH8ZZRpaHEW6E8z3GzwQseIYL/gv5JcGU9iKZQSPdGxh8tgdv9jNnF/7/sJBFDZyza3YITK4Pm9mKs0pnGsUBuSfhTBh+mUEyGAqgCxnOROB1sJh3aq2B07T2C6W0Pg8e6vBVLg57hJH8WKG4aqy03MP5Swh2SEQORMOPdF0QETSCzLKBFwMiigIoJBPUg3EuIjB1tp8FeHqPJKcnUcYiCHMtZxIs/JiXPBXhLh7w+hbzBmuOq3Y++G7QYM2ETwfXZzd0tvjXPfeQjTk/Nm492xV3xP/KRX8rxsGTgBgXVIHoL7vzdbVU/2LoSJauKeYO2/b7b5KW4qsfwhGW2x04HoXJwqC63k3INLanwuzgnPd0+wvcxIzVDCOHRdKX5VqFycch53i9l7z7hKn9FYcifxHEAIBeA7wOj7+UTHaiz3tO7e1CB9aIsiYtnqxP38/DCtVDK0nllVT3meTsY7rCTJeYKOdQeS+brfznT4cJuPVSS3ZGFZx0KTMcFLarUcBkj/+PDp/JBJbOWZ+UxykxPJdqah+8FH0+V8mPg+6cNUdEAAUBc8zqJyTcBzcngHIUIITA07tflkiP+7VN3vS/Q/WpWdvZ8eFS0mMN3Ldu+527jR/3j6seYdeLInvLdy6NW5Twd6ggW6ohNB8X6xOAuQM9TMYQ+VOQdRfZk36nhvoaLSUMZYsPTpHRvJ8tdd6XhlyIcBcO7DPuNMGsqhR+eUzMyeXg4n8mT8Kd6z58FAFwT3GXB2g16Zs7bgUKUAJfq/CJVJinO5Jpjtfj+P7k87UQSJT+qknWFaFPXJS+i3fZ6hmQwZpzMKfSD1BAuAWaG5BYdYcjdxc7ihUMmVKA7l3oAFqlYyWCsivTRtEfSfBCaJSvtRxvnQ+vRJjFT71aVV1LRVx2wISrWiNUY8FzOXJmFUy77fIx0mrzKMUBcSMcr0CIH3GEl9rEWY71EozjWkCrZbme7TIbdRozOpKRl4xpQIRT9TUGUTG0e3+wXlzUJnFMbMizOakPAcS7fb3enn523I2Z45L5M2j1YnUltNdIwqkmyNh+zJzyen5NqGMKvxnvKEQBkoGrTQ+MkYbB4lbBY8UX472iYbDixR06CNAqsprksJ1SNvy4fAHqgxphFsNgj3LENJpIg45cItcEuJ4CejvkbTgSEn4QWZ/Fbbz0yXFVBKsmw4vkjHJ3XMGPQojnCkRZmb0dFsvm6xjr2cLSKVT5TkayobLtKZjDlLcHm/xV7+cThCe6KS24yvvpmcKXFADpG7nbQWk2N4yZSgao7f2YL8CbIkmUW+fDw3mfiDHKpXRR218lotVdmGN2aEFQpuoJ6yGLyD8oojPKfmbNURVYZQ0DhkmPpZw7/zmxZVP3GItNj2pVJvXn4p1Fp/CL/8zf/y9FeTP9l57cXCApd98fiTiLbUkE1elLyjEGxXx6zKq0NSE+SfNYcaU0NtiNRcXCrxrL1/irtSnTBUNFh/J7zJ2kL8eESKNDWZCLOPsMx73U42f1MxTbD0p54TGiXiMx4Vi2Gl0S1N5DiV2/MVbAGtAqdF/TzSknJ0KLzVB5fkxZocWX+pL5Ibdhtrsy3VWjjsQhidhhW6X3eK1I/8j9fYCemdlIk3XouimBPcdliRWDKtyjrfEi2JgcEimf4+6pVzKCbrpCHGOu/UKTU2w/pJPJrJcebspqbHIjxSsXEpp0sPdwmHqgOxf4iqaoeqDSq7WaFxo0L1nlHrQ+t6jb+V6dwU8XZZ0li/KJZqUQWyyHBxMju+R5AxOYJu68hCzLqPW2pgXpNOdztrv8A2mrmSDuUDlFbAiOj/eEoUyaGmtpq6xfxj972vD7G4neY1n2BgI8yp6gDtlNk+Mw4EGUliY6IyNlh/Z8XzFvZyu2Ci5VRuhJjcbMGWeVpw0NJFsuXj8ocUi0mG4fgYMXtVdO9opsh6DDR1OOP8A5c/uhTMxWNxKRYB4tGlfOvLO6xZ3TbimKzwIzcZJpvVdx6G+4ty2If8KnZVSpe52OK6cmv325tVl5avhcGlP6L4m2WFUTw/ZvJGw/9lXm5fUraqhkW2V/VEE63iDYcu3UtVlnT7JqY0KvrgNptGBahGv+wvk6dhId2dZoplW0Z4e66aLEeRrEwOzeW7yMJ9cDSucMGsrANc0y6o7Y4yTPbFlRvH2fmdW0/hRMlSrrmro40fEcyJ/vxXmAsAZ75PBb/kv0YV84K+0Vn4SwCAR50OEQAAj5e86R4Y9t3Ea8IfAOgw03NeiRaEAfz9Pfrc8LK8TA2RaRIAXh9Y7AFVlgsolGCTflKEARiFBJw9Aq/IAbfPYd80D9zDPjhnBe7cJgDPDaCBs4/brAEowTglDw6dO0q1Lr+UiNgBJYZrkxLnYISSYEWtJIWwAk16KYBIHTRK1apSrkG9Fs7SlKnQqlapJllmu0mzqqBxBXcu3DAXKDq42UmnknOQzBMeJuwezON6X/aZ61Eczuz2EdJFSxKY6LB0fCDCbzmdzgBURaLKgmAXAfa3nAc3F14m1IGXFUlzWk1crp0LlVOpxYuK5NT8gbIbK0ObNKblAgf2Bv4jAQAA);
			}
		</style><clipPath id="SVGID_00000045615448653943012690000000638754117711156656_"
			><use xlink:href="#SVGID_1_" /></clipPath
		><path
			id="SVGID_1_"
			d="m847.5 617.48c0 136.96-111.03 248-248 248-136.97 0-248-111.03-248-248 0-136.97 111.04-248 248-248 136.97 0 248 111.04 248 248z"
		/></defs
	><mask id="mask-image-crop-wXzwZ5s162Swzbn-HDebe" fill="#fff"
		><rect x="35.34" y="55.189" width="166" height="146" /></mask
	><g transform="translate(-25.34 -21.963)" mask="url(#mask-image-crop-wXzwZ5s162Swzbn-HDebe)"
		><use
			width="201.34012"
			height="201.18867"
			href="#image-crop-413635151d9e6ef5ac51a63e2bd501140953e76e9f7c606fa2f8a78e45d8d5b6ef0a524bba2a68f0b44dda5286d8ee8c-2426746997"
		/></g
	><g transform="translate(23.145 15.66) rotate(0 69.88 12.5)"
		><text
			y="17.620001"
			dominant-baseline="alphabetic"
			fill="#f08c00"
			font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
			font-size="20px"
			style="white-space:pre"
			><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'">Tracker Group</tspan
			></text
		></g
	><mask /><g transform="translate(358.4 35) rotate(0 68.977 68.977)"
		><use
			width="138"
			height="138"
			href="#image-250b02f3e0ab535ae1dead582a2a45474a44662a6f834a5523c81d7d2e6b595fe5acbcbf3c2a529022e9e6a0fa730089"
		/></g
	><g transform="translate(389.7 17.843)"
		><text
			y="17.620001"
			dominant-baseline="alphabetic"
			fill="#f08c00"
			font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
			font-size="20px"
			style="white-space:pre"
			><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'">Polluter</tspan></text
		></g
	><g id="OBJECTS" transform="matrix(.27367 0 0 .27367 354.07 36.623)" stroke-width="1.827"
		><path
			d="m461.63 390.71c0-116.88-94.749-211.63-211.63-211.63s-211.63 94.749-211.63 211.63"
			fill="#ffde25"
		/><g transform="translate(-3.654)"
			><polyline
				points="258.3 330.16 297.57 299.69 326.04 319.89 369.88 292.55 426.41 334.94 423.61 359.95 278.07 366.29"
				fill="#fbb62d"
			/><g fill="#4e8d3a"
				><path
					d="m353.01 367.45c-0.088 0-0.178-8e-3 -0.268-0.023-0.815-0.147-1.357-0.928-1.21-1.742 6.411-35.573-9.422-56.815-9.583-57.025-0.502-0.658-0.377-1.6 0.28-2.103 0.656-0.502 1.596-0.381 2.101 0.277 0.689 0.898 16.814 22.431 10.154 59.381-0.13 0.726-0.762 1.235-1.474 1.235z"
				/><path
					d="m346.53 313.39s4.52-10.143-7.888-11.453c-2.181 12.019 7.888 11.453 7.888 11.453z"
				/><path
					d="m349.63 319.82s10.878 2.231 9.487-10.168c-12.206 0.457-9.487 10.168-9.487 10.168z"
				/><path
					d="m349.83 319.59s-6.975-8.64-13.788 1.813c9.71 7.411 13.788-1.813 13.788-1.813z"
				/><path
					d="m352.38 330.66s9.958 4.914 11.753-7.433c-11.924-2.65-11.753 7.433-11.753 7.433z"
				/><path
					d="m352.63 330.49s-4.56-10.125-13.798-1.739c7.516 9.628 13.798 1.739 13.798 1.739z"
				/><path
					d="m354.2 343.72s8.977 6.536 12.847-5.325c-11.3-4.64-12.847 5.325-12.847 5.325z"
				/><path
					d="m354.48 343.59s-2.771-10.753-13.301-4.061c5.769 10.767 13.301 4.061 13.301 4.061z"
				/></g
			><g fill="#6ea843"
				><path
					d="m431.43 334.42c-0.213 0-0.43-0.046-0.637-0.142-0.75-0.352-1.072-1.245-0.72-1.995 15.957-33.986 41.569-42.211 42.651-42.545 0.791-0.239 1.629 0.199 1.874 0.99s-0.198 1.631-0.989 1.876c-0.253 0.079-25.459 8.235-40.82 40.954-0.256 0.544-0.796 0.862-1.359 0.862z"
				/><path
					d="m467.13 293.82s2.185-10.887 13.062-4.774c-5.179 11.063-13.062 4.774-13.062 4.774z"
				/><path
					d="m460.88 297.27s-10.162-4.477-1.851-13.783c9.689 7.438 1.851 13.783 1.851 13.783z"
				/><path
					d="m460.85 296.97s10.689-3.008 10.195 9.459c-12.208 0.423-10.195-9.459-10.195-9.459z"
				/><path
					d="m452.37 304.52s-10.964-1.757-5.282-12.864c11.258 4.74 5.282 12.864 5.282 12.864z"
				/><path
					d="m452.26 304.23s9.579-5.617 12.258 6.568c-11.702 3.502-12.258-6.568-12.258-6.568z"
				/><path
					d="m443.33 314.12s-11.103 0.134-7.394-11.778c11.9 2.756 7.394 11.778 7.394 11.778z"
				/><path
					d="m443.17 313.85s8.483-7.165 13.197 4.387c-10.936 5.441-13.197-4.387-13.197-4.387z"
				/><path
					d="m333.33 270.29c0-14.337-11.622-53.19-25.959-53.19s-25.959 38.853-25.959 53.19 11.622 25.959 25.959 25.959 25.959-11.622 25.959-25.959z"
				/></g
			><g fill="#13304e"
				><path
					d="m307.37 333.28c-0.829 0-1.5-0.672-1.5-1.5v-73.128c0-0.828 0.671-1.5 1.5-1.5s1.5 0.672 1.5 1.5v73.128c0 0.828-0.672 1.5-1.5 1.5z"
				/><path
					d="m307.37 290c-0.38 0-0.761-0.144-1.053-0.432l-9.709-9.567c-0.59-0.581-0.597-1.531-0.016-2.121s1.531-0.597 2.121-0.016l9.709 9.567c0.59 0.581 0.597 1.531 0.016 2.121-0.293 0.298-0.681 0.448-1.068 0.448z"
				/><path
					d="m307.37 276.4c-0.383 0-0.765-0.145-1.058-0.437-0.587-0.585-0.589-1.534-5e-3 -2.121l6.634-6.667c0.585-0.588 1.534-0.59 2.122-6e-3 0.587 0.585 0.589 1.534 5e-3 2.121l-6.634 6.667c-0.294 0.296-0.679 0.443-1.064 0.443z"
				/><path
					d="m307.37 311.23c-0.43 0-0.856-0.184-1.153-0.54-0.53-0.636-0.444-1.582 0.192-2.112l8.043-6.702c0.638-0.53 1.583-0.444 2.113 0.192s0.444 1.582-0.192 2.112l-8.043 6.702c-0.282 0.234-0.622 0.348-0.96 0.348z"
				/></g
			><path
				d="m351.8 273.6c0-18.435 14.944-68.392 33.379-68.392s33.379 49.958 33.379 68.392-14.944 33.379-33.379 33.379-33.379-14.944-33.379-33.379z"
				fill="#6ea843"
			/><g fill="#13304e"
				><path
					d="m385.17 354.16c-0.829 0-1.5-0.672-1.5-1.5v-94.029c0-0.828 0.671-1.5 1.5-1.5s1.5 0.672 1.5 1.5v94.029c0 0.828-0.671 1.5-1.5 1.5z"
				/><path
					d="m385.17 298.52c-0.388 0-0.775-0.149-1.068-0.447-0.581-0.59-0.575-1.54 0.016-2.121l12.484-12.301c0.589-0.582 1.54-0.574 2.121 0.016 0.582 0.59 0.575 1.54-0.016 2.121l-12.484 12.301c-0.292 0.288-0.673 0.431-1.053 0.431z"
				/><path
					d="m385.17 281.03c-0.385 0-0.77-0.147-1.063-0.442l-8.531-8.572c-0.584-0.587-0.582-1.536 5e-3 -2.121 0.587-0.583 1.537-0.582 2.122 6e-3l8.531 8.572c0.584 0.587 0.582 1.536-5e-3 2.121-0.293 0.291-0.676 0.436-1.059 0.436z"
				/><path
					d="m385.17 325.82c-0.338 0-0.679-0.114-0.96-0.348l-10.342-8.618c-0.636-0.53-0.722-1.477-0.192-2.112 0.53-0.637 1.475-0.723 2.113-0.192l10.342 8.618c0.636 0.53 0.722 1.477 0.192 2.112-0.297 0.357-0.723 0.54-1.153 0.54z"
				/></g
			><path
				d="m447.73 347.09c0.318-11.124-3.002-21.627-10.618-26.635-16.495-10.847-42.552 0-40.342 22.34-28.737-4.509-30.013 16.786-30.013 16.786s-8.671-15.592-29.671-4.36c1.105-24.689-21-39.416-40.342-27.604-11.053-34.609-46.745-37.746-46.745-37.746v91.359l172.03-0.383c3.984 6.781 11.35 1.274 19.783 1.274 12.666 0 22.934-0.206 22.934-12.872 1e-3 -10.619-7.217-19.548-17.013-22.159z"
				fill="#4e8d3a"
			/><path
				d="m449.08 370.51c0 14.01-11.357 16.723-25.366 16.723s-25.367-2.714-25.367-16.723c0-14.01 11.357-25.367 25.367-25.367s25.366 11.358 25.366 25.367z"
				fill="#13304e"
				opacity=".2"
			/><path
				d="m383.47 377.39s-9.577-8.476-7.729-11.43 8.905 3.935 8.905 3.935-6.889-11.634-2.352-13.714 6.889 11.53 6.889 11.53 1.344-11.085 5.041-10.245c3.696 0.84 0.168 13.32 0.168 13.32s3.865-8.843 7.393-7.555c3.528 1.287-4.369 15.052-4.369 15.052"
				fill="#6ea843"
			/><path d="m250 378.28v-43.814s47.85-7.55 51.166 43.814" fill="#13304e" opacity=".2" /><path
				d="m251.63 376.15s1.215-23.439 6.251-23.526c5.035-0.087 2.604 15.912 2.604 15.912s4.256-15.912 8.966-14.103c4.351 1.671-3.658 15.629-3.658 15.629s8.48-9.22 11.535-5.997c3.413 3.603-10.939 14.212-10.939 14.212"
				fill="#6ea843"
			/><g fill="#a4cd49"
				><path
					d="m411.33 268.23c0 3.775-3.06 6.836-6.836 6.836-3.775 0-6.836-3.061-6.836-6.836s3.06-6.836 6.836-6.836c3.775 0 6.836 3.061 6.836 6.836z"
				/><path
					d="m407.63 251.38c0 1.462-1.185 2.648-2.648 2.648-1.462 0-2.648-1.185-2.648-2.648 0-1.462 1.185-2.648 2.648-2.648 1.463 1e-3 2.648 1.186 2.648 2.648z"
				/><circle cx="366.38" cy="285.2" r="5.673" /><path
					d="m322.66 276.55c0 1.646-1.335 2.981-2.981 2.981s-2.981-1.335-2.981-2.981 1.335-2.981 2.981-2.981 2.981 1.335 2.981 2.981z"
				/><circle cx="293.91" cy="263.62" r="6.067" /></g
			><g fill="#13304e"
				><circle cx="319.47" cy="370.78" r="12.207" opacity=".2" /><circle
					cx="304.21"
					cy="356.18"
					r="3.048"
					opacity=".2"
				/><circle cx="436.62" cy="337.34" r="3.048" opacity=".2" /><path
					d="m319.91 349.31c0 2.483-2.013 4.495-4.496 4.495s-4.495-2.013-4.495-4.495c0-2.483 2.013-4.496 4.495-4.496 2.483 0 4.496 2.013 4.496 4.496z"
					opacity=".2"
				/><path
					d="m271.08 322.09c0 3.529-2.861 6.39-6.39 6.39s-6.39-2.861-6.39-6.39 2.861-6.39 6.39-6.39 6.39 2.861 6.39 6.39z"
					opacity=".2"
				/></g
			><g fill="#dbebb7"
				><path
					d="m288.01 170.19h69.303s-4.397-16.271-19.029-11.818c-3.343-21.531-32.318-23.299-34.93 1.322-11.296-2.633-15.344 10.496-15.344 10.496z"
				/><path
					d="m374.82 145.76h81.442s-6.904-12.076-22.333-7.717c-0.514-16.214-24.209-27.035-41.659-9.659-13.886-5.011-22.557 9.934-17.45 17.376z"
				/><path
					d="m403.34 101.09h-99.533s8.437-14.758 27.294-9.431c0.629-19.815 29.587-33.04 50.913-11.805 16.971-6.125 27.567 12.14 21.326 21.236z"
				/></g
			><g fill="#13304e"
				><path
					d="m419.74 213.34c-0.1 0-0.201-0.015-0.299-0.046-0.392-0.123-0.669-0.473-0.698-0.883-0.2-2.796-4.275-4.456-4.316-4.473-0.512-0.205-0.763-0.786-0.559-1.298 0.204-0.513 0.785-0.763 1.296-0.561 0.182 0.072 3.802 1.538 5.115 4.416 3.089-2.11 7.432-1.038 7.643-0.984 0.534 0.137 0.856 0.68 0.72 1.214-0.136 0.535-0.68 0.858-1.214 0.724-0.048-0.012-4.748-1.159-6.91 1.519-0.193 0.24-0.481 0.372-0.778 0.372z"
				/><path
					d="m435.66 193.96c-0.023 0-0.046-1e-3 -0.069-2e-3 -0.41-0.028-0.761-0.304-0.885-0.696-0.544-1.718-3.472-2.182-3.501-2.186-0.547-0.078-0.927-0.585-0.849-1.131 0.078-0.547 0.588-0.93 1.131-0.849 0.137 0.02 2.743 0.412 4.254 2.07 1.907-1.837 4.966-1.815 5.126-1.814 0.552 8e-3 0.993 0.463 0.985 1.015s-0.478 1.018-1.015 0.985c-0.014 6e-3 -3.299-0.012-4.274 2.038-0.167 0.35-0.519 0.57-0.903 0.57z"
				/><path
					d="m402.2 186.13c-0.348 0-0.676-0.182-0.858-0.488-1.436-2.409-5.821-2.063-5.866-2.057-0.545 0.043-1.034-0.359-1.082-0.909-0.048-0.549 0.357-1.034 0.907-1.083 0.195-0.017 4.087-0.334 6.554 1.648 1.812-3.274 6.173-4.267 6.385-4.313 0.538-0.116 1.07 0.223 1.189 0.762 0.119 0.538-0.222 1.072-0.76 1.192-0.048 0.011-4.762 1.098-5.491 4.462-0.087 0.401-0.411 0.709-0.816 0.775-0.054 6e-3 -0.108 0.011-0.162 0.011z"
				/></g
			></g
		><g id="smoke" opacity={smoke.opacity}
			><path
				d="m221.34 162.18s-2.999-3.097 0-7.976c-13.702 2.91-30.194-5.249-33.563-14.566-9.867 10.769-26.287 12.447-31.235-3.878-6.241 0-7.91-10.422-1.697-12.901 1.225-5.762 5.601-3.413 5.601-3.413s14.177-11.376 20.843 4.317c10.177-1.952 9.165 7.208 9.165 7.208s32.335-9.891 33.194 12.774c7.234-0.178 6.38 6.554 6.38 6.554s4.884 4.977-1.239 11.882"
				fill="#7b8c9d"
			/><path
				d="m168.7 137.52c0.233 1.562-0.844 3.018-2.407 3.251-1.562 0.233-3.018-0.844-3.251-2.407-0.233-1.562 0.844-3.018 2.407-3.251 1.562-0.233 3.018 0.844 3.251 2.407z"
				fill="#919fad"
			/><path
				d="m179.39 139.1c0.32 2.143-1.158 4.139-3.3 4.458-2.143 0.32-4.139-1.158-4.458-3.3-0.32-2.142 1.158-4.139 3.3-4.458 2.142-0.32 4.138 1.158 4.458 3.3z"
				fill="#919fad"
			/><path
				d="m187.35 117.1s-6.112-3.222-3.082-11.429c-7.165 5.097-20.464-1.687-19.199-12.654-9.35 4.749-25.952 1.621-19.682-16.854-7.038-0.497-10.174-14.473 0.52-16.327-1.334-9.86 29.406-26.829 42.719 1.877 9.942-2.516 13.518 12.426 3.914 15.665 5.685 1.873 8.574 14.265 0.259 19.014 15.404-1.65 16.834 12.74 15.056 19.84"
				fill="#7b8c9d"
			/><g fill="#919fad"
				><path
					d="m159.29 87.424c0.226 1.517-0.82 2.93-2.336 3.156-1.517 0.226-2.93-0.819-3.156-2.336s0.82-2.93 2.336-3.156c1.516-0.227 2.929 0.819 3.156 2.336z"
				/><path
					d="m172.46 84.507c0.303 2.033-1.099 3.927-3.132 4.231-2.033 0.303-3.927-1.099-4.231-3.132-0.303-2.033 1.099-3.927 3.132-4.231 2.034-0.303 3.928 1.099 4.231 3.132z"
				/><path
					d="m181.75 95.488c0.456 3.056-1.651 5.902-4.707 6.359s-5.902-1.651-6.359-4.707c-0.456-3.056 1.651-5.902 4.707-6.358 3.056-0.457 5.903 1.651 6.359 4.706z"
				/></g
			><path
				d="m71.691 95.01s12.473-1.01 15.96 10.47c3.524 11.602-6.383 20.801-6.383 20.801s3.193 0.415 2.659 3.866c4.285-1.399 8.959 1.771 8.085 6.632 7.752 2.84 8.499 13.57 0.663 17.557 10.002 9.101-1.815 22.788-1.815 22.788h-11.075s-1.546-7.502-3.006-10.384c-12.784 2.55-15.239-8.59-15.239-8.59s-11.102-0.998-10.16-13.786c-14.819 1.98-19.234-13.111-11.477-20.786-15.38-10.096-7.432-41.494 14.676-36.325 3.507-4.819 6.867-0.203 6.867-0.203s9.295-2.804 10.245 7.96z"
				fill="#7b8c9d"
			/><g fill="#919fad"
				><path
					d="m52.431 135.5c0.087 2.937-2.224 5.389-5.161 5.476s-5.389-2.224-5.476-5.161 2.224-5.389 5.161-5.476c2.938-0.087 5.39 2.223 5.476 5.161z"
				/><path
					d="m60.553 146.27c0.041 1.398-1.059 2.565-2.457 2.607-1.398 0.041-2.565-1.059-2.607-2.457-0.041-1.398 1.059-2.565 2.457-2.607 1.399-0.041 2.566 1.059 2.607 2.457z"
				/><path
					d="m92.133 159.57c0.041 1.398-1.059 2.565-2.457 2.607-1.398 0.041-2.565-1.059-2.607-2.457-0.041-1.398 1.059-2.565 2.457-2.607 1.399-0.041 2.566 1.059 2.607 2.457z"
				/><path
					d="m66.666 137.69c0.071 2.387-1.807 4.378-4.193 4.449-2.387 0.071-4.378-1.807-4.449-4.193s1.807-4.378 4.193-4.449 4.378 1.806 4.449 4.193z"
				/></g
			></g
		><g id="smokestack" transform="translate(0 {smokestack.y})"
			><rect x="221.34" y="164.75" width="7.448" height="87.95" fill="#38516a" /><rect
				x="219.24"
				y="160.41"
				width="11.635"
				height="8.672"
				fill="#13304e"
			/><rect x="221.34" y="174.17" width="7.448" height="5.469" fill="#13304e" /><g fill="#7b8c9d"
				><rect x="221.34" y="184.55" width="7.448" height="2.643" /><rect
					x="221.34"
					y="190.46"
					width="7.448"
					height="2.643"
				/><rect x="221.34" y="196.36" width="7.448" height="2.643" /><rect
					x="221.34"
					y="202.27"
					width="7.448"
					height="2.643"
				/></g
			><rect x="184.26" y="117.98" width="23.371" height="147.6" fill="#13304e" /><g fill="#fff"
				><rect x="184.26" y="171.73" width="23.371" height="2.439" /><rect
					x="184.26"
					y="176.9"
					width="23.371"
					height="2.439"
				/><rect x="184.26" y="182.08" width="23.371" height="2.439" /><rect
					x="184.26"
					y="187.25"
					width="23.371"
					height="2.439"
				/></g
			><g fill="#38516a"
				><path
					d="m206.25 113.87h-20.607c-2.118 0-3.835 1.717-3.835 3.835v0.536c0 2.118 1.717 3.835 3.835 3.835h20.607c2.118 0 3.835-1.717 3.835-3.835v-0.536c0-2.118-1.717-3.835-3.835-3.835z"
				/><rect x="184.26" y="128.19" width="23.371" height="8.892" /><rect
					x="184.26"
					y="143.19"
					width="23.371"
					height="8.892"
				/><rect x="184.26" y="158.19" width="23.371" height="8.892" /></g
			><path
				d="m250 51.712c-1.86 0-3.367 1.507-3.367 3.367v325.63h6.734v-325.63c0-1.859-1.507-3.367-3.367-3.367z"
				fill="#13304e"
			/><g fill="#13304e"
				><polygon
					transform="translate(3.7586e-6)"
					points="68.938 377.45 68.938 186.09 176.39 195.1 176.39 377.45"
				/><rect
					transform="translate(3.7586e-6)"
					x="78.4"
					y="174.17"
					width="15.663"
					height="33.613"
				/><rect
					transform="translate(3.7586e-6)"
					x="101.51"
					y="179.64"
					width="4.668"
					height="19.257"
				/><rect
					transform="translate(3.7586e-6)"
					x="112.77"
					y="167.74"
					width="9.893"
					height="33.613"
				/><rect
					transform="translate(3.7586e-6)"
					x="65.465"
					y="200.39"
					width="52.791"
					height="16.71"
				/><path
					d="m94.759 171.82h-17.055c-0.697 0-1.262 0.565-1.262 1.262v2.177c0 0.697 0.565 1.262 1.262 1.262h17.056c0.697 0 1.262-0.565 1.262-1.262v-2.177c0-0.696-0.565-1.262-1.263-1.262z"
				/></g
			><g fill="#38516a"
				><path
					d="m84.084 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.962 2.148-2.148 2.148z"
				/><path
					d="m98.617 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.962 2.148-2.148 2.148z"
				/><path
					d="m113.15 235.58h-3.536c-1.186 0-2.148-0.962-2.148-2.148v-8.585c0-1.186 0.962-2.148 2.148-2.148h3.536c1.186 0 2.148 0.962 2.148 2.148v8.585c0 1.186-0.961 2.148-2.148 2.148z"
				/></g
			></g
		><rect x="51.438" y="275.51" width="113.85" height="105.31" fill="#13304e" /><polygon
			points="51.438 264.7 51.438 275.51 165.29 275.51 165.29 226.5"
			fill="#38516a"
		/><g stroke-width="1.827"
			><rect x="58.614" y="283.81" width="16.063" height="25.925" fill="#38516a" /><rect
				x="61.836"
				y="288.5"
				width="9.619"
				height="16.532"
				fill="#fff"
			/><rect x="80.785" y="283.81" width="16.063" height="25.925" fill="#38516a" /><rect
				x="84.008"
				y="288.5"
				width="9.618"
				height="16.532"
				fill="#fff"
			/><rect x="102.96" y="283.81" width="16.063" height="25.925" fill="#38516a" /><rect
				x="106.18"
				y="288.5"
				width="9.619"
				height="16.532"
				fill="#fff"
			/><rect x="58.614" y="315.75" width="16.063" height="25.925" fill="#38516a" /><rect
				x="61.836"
				y="320.45"
				width="9.619"
				height="16.532"
				fill="#fff"
			/><rect x="80.785" y="315.75" width="16.063" height="25.925" fill="#38516a" /><rect
				x="84.008"
				y="320.45"
				width="9.618"
				height="16.532"
				fill="#fff"
			/><rect x="102.96" y="315.75" width="16.063" height="25.925" fill="#38516a" /><rect
				x="106.18"
				y="320.45"
				width="9.619"
				height="16.532"
				fill="#fff"
			/></g
		><rect x="51.438" y="349.31" width="113.85" height="31.504" fill="#38516a" /><g fill="#13304e"
			><rect x="54.208" y="352.97" width="8.812" height="4.489" /><rect
				x="68.507"
				y="352.97"
				width="8.812"
				height="4.489"
			/><rect x="82.806" y="352.97" width="8.812" height="4.489" /><rect
				x="97.105"
				y="352.97"
				width="8.812"
				height="4.489"
			/><rect x="111.4" y="352.97" width="8.812" height="4.489" /><rect
				x="125.7"
				y="352.97"
				width="8.812"
				height="4.489"
			/><rect x="140" y="352.97" width="8.812" height="4.489" /><rect
				x="154.3"
				y="352.97"
				width="8.812"
				height="4.489"
			/><rect x="61.058" y="359.58" width="8.812" height="4.489" /><rect
				x="75.358"
				y="359.58"
				width="8.812"
				height="4.489"
			/><rect x="89.657" y="359.58" width="8.812" height="4.489" /><rect
				x="103.96"
				y="359.58"
				width="8.812"
				height="4.489"
			/><rect x="118.26" y="359.58" width="8.812" height="4.489" /><rect
				x="132.55"
				y="359.58"
				width="8.812"
				height="4.489"
			/><rect x="146.85" y="359.58" width="8.812" height="4.489" /><rect
				x="54.208"
				y="366.29"
				width="8.812"
				height="4.489"
			/><rect x="68.507" y="366.29" width="8.812" height="4.489" /><rect
				x="82.806"
				y="366.29"
				width="8.812"
				height="4.489"
			/><rect x="97.105" y="366.29" width="8.812" height="4.489" /><rect
				x="111.4"
				y="366.29"
				width="8.812"
				height="4.489"
			/><rect x="125.7" y="366.29" width="8.812" height="4.489" /><rect
				x="140"
				y="366.29"
				width="8.812"
				height="4.489"
			/><rect x="154.3" y="366.29" width="8.812" height="4.489" /><rect
				x="61.058"
				y="372.9"
				width="8.812"
				height="4.489"
			/><rect x="75.358" y="372.9" width="8.812" height="4.489" /><rect
				x="89.657"
				y="372.9"
				width="8.812"
				height="4.489"
			/><rect x="103.96" y="372.9" width="8.812" height="4.489" /><rect
				x="118.26"
				y="372.9"
				width="8.812"
				height="4.489"
			/><rect x="132.55" y="372.9" width="8.812" height="4.489" /><rect
				x="146.85"
				y="372.9"
				width="8.812"
				height="4.489"
			/></g
		><rect x="133.37" y="275.51" width="113.85" height="105.31" fill="#38516a" /><polygon
			points="133.37 275.51 247.22 275.51 247.22 226.5 133.37 264.7"
			fill="#7b8c9d"
		/><g stroke-width="1.827"
			><rect x="140.55" y="283.81" width="16.063" height="25.925" fill="#13304e" /><rect
				x="143.77"
				y="288.5"
				width="9.618"
				height="16.532"
				fill="#fff"
			/><rect x="162.72" y="283.81" width="16.063" height="25.925" fill="#13304e" /><rect
				x="165.94"
				y="288.5"
				width="9.619"
				height="16.532"
				fill="#fff"
			/><rect x="184.89" y="283.81" width="16.063" height="25.925" fill="#13304e" /><rect
				x="188.11"
				y="288.5"
				width="9.618"
				height="16.532"
				fill="#fff"
			/><rect x="140.55" y="315.75" width="16.063" height="25.925" fill="#13304e" /><rect
				x="143.77"
				y="320.45"
				width="9.618"
				height="16.532"
				fill="#fff"
			/><rect x="162.72" y="315.75" width="16.063" height="25.925" fill="#13304e" /><rect
				x="165.94"
				y="320.45"
				width="9.619"
				height="16.532"
				fill="#fff"
			/><rect x="184.89" y="315.75" width="16.063" height="25.925" fill="#13304e" /><rect
				x="188.11"
				y="320.45"
				width="9.618"
				height="16.532"
				fill="#fff"
			/></g
		><rect x="133.37" y="349.31" width="113.85" height="31.504" fill="#13304e" /><g opacity=".2"
			><g fill="#13304e" stroke-width="1.827"
				><rect x="136.14" y="352.97" width="8.812" height="4.489" /><rect
					x="150.44"
					y="352.97"
					width="8.812"
					height="4.489"
				/><rect x="164.74" y="352.97" width="8.812" height="4.489" /><rect
					x="179.04"
					y="352.97"
					width="8.812"
					height="4.489"
				/><rect x="193.34" y="352.97" width="8.812" height="4.489" /><rect
					x="207.64"
					y="352.97"
					width="8.812"
					height="4.489"
				/><rect x="221.94" y="352.97" width="8.812" height="4.489" /><rect
					x="236.24"
					y="352.97"
					width="8.812"
					height="4.489"
				/><rect x="142.99" y="359.58" width="8.812" height="4.489" /><rect
					x="157.29"
					y="359.58"
					width="8.812"
					height="4.489"
				/><rect x="171.59" y="359.58" width="8.812" height="4.489" /><rect
					x="185.89"
					y="359.58"
					width="8.812"
					height="4.489"
				/><rect x="200.19" y="359.58" width="8.812" height="4.489" /><rect
					x="214.49"
					y="359.58"
					width="8.812"
					height="4.489"
				/><rect x="228.79" y="359.58" width="8.812" height="4.489" /><rect
					x="136.14"
					y="366.29"
					width="8.812"
					height="4.489"
				/><rect x="150.44" y="366.29" width="8.812" height="4.489" /><rect
					x="164.74"
					y="366.29"
					width="8.812"
					height="4.489"
				/><rect x="179.04" y="366.29" width="8.812" height="4.489" /><rect
					x="193.34"
					y="366.29"
					width="8.812"
					height="4.489"
				/><rect x="207.64" y="366.29" width="8.812" height="4.489" /><rect
					x="221.94"
					y="366.29"
					width="8.812"
					height="4.489"
				/><rect x="236.24" y="366.29" width="8.812" height="4.489" /><rect
					x="142.99"
					y="372.9"
					width="8.812"
					height="4.489"
				/><rect x="157.29" y="372.9" width="8.812" height="4.489" /><rect
					x="171.59"
					y="372.9"
					width="8.812"
					height="4.489"
				/><rect x="185.89" y="372.9" width="8.812" height="4.489" /><rect
					x="200.19"
					y="372.9"
					width="8.812"
					height="4.489"
				/><rect x="214.49" y="372.9" width="8.812" height="4.489" /><rect
					x="228.79"
					y="372.9"
					width="8.812"
					height="4.489"
				/></g
			></g
		><g fill="#7b8c9d"
			><path
				d="m239.3 292.55h-28.954c-0.742 0-1.343-0.602-1.343-1.343 0-0.742 0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343s-0.602 1.343-1.343 1.343z"
			/><path
				d="m239.3 303.03h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343 0 0.741-0.602 1.343-1.343 1.343z"
			/><path
				d="m239.3 313.51h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343 0 0.741-0.602 1.343-1.343 1.343z"
			/><path
				d="m239.3 323.99h-28.954c-0.742 0-1.343-0.602-1.343-1.343 0-0.742 0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.601 1.343 1.343s-0.602 1.343-1.343 1.343z"
			/><path
				d="m239.3 334.46h-28.954c-0.742 0-1.343-0.601-1.343-1.343s0.601-1.343 1.343-1.343h28.954c0.742 0 1.343 0.602 1.343 1.343s-0.602 1.343-1.343 1.343z"
			/></g
		><ellipse cx="250" cy="429.49" rx="141.42" ry="30.736" fill="#38516a" /><path
			d="m428.91 395.88h-357.81v33.548c0 5.848 4.741 10.589 10.589 10.589h336.64c5.848 0 10.589-4.741 10.589-10.589v-33.548z"
			fill="#13304e"
		/><path
			d="m456.03 382.98h-412.07v20.443c0 5.848 4.741 10.589 10.589 10.589h390.89c5.848 0 10.589-4.741 10.589-10.589v-20.443z"
			fill="#a4cd49"
		/><path
			d="m469.87 389.08h-439.75c-4.337 0-7.854-3.516-7.854-7.854 0-4.337 3.516-7.853 7.854-7.853h439.75c4.337 0 7.854 3.516 7.854 7.853 0 4.338-3.516 7.854-7.853 7.854z"
			fill="#6ea843"
		/></g
	><g transform="matrix(.19988 0 0 .19988 -33.545 -13.576)"
		><g stroke-width="2.5016"
			><path
				d="m847.5 617.48c0 136.96-111.03 248-248 248-136.97 0-248-111.03-248-248 0-136.97 111.04-248 248-248 136.97 0 248 111.04 248 248z"
				fill="#c7b299"
			/><g
				fill="none"
				stroke="#fff"
				stroke-dasharray="15.0093, 15.0093"
				stroke-miterlimit="10"
				stroke-width="5.0031"
				><path
					d="m804.58 746.62h-399.25c-25.943 0-46.969-22.909-46.969-51.176v-2.325c0-28.26 21.026-51.169 46.969-51.169h290.36"
				/><path d="m697.82 500.07c-34.2-0.375-66.379-0.375-99.495 0" /><path
					d="m620.96 500.07h126.49c35.168 0 63.67 31.054 63.67 69.367v3.151c0 38.31-28.502 69.365-63.67 69.365h-303.69"
				/></g
			><g stroke-width="2.5016"
				><rect x="679.79" y="528.64" width="101.59" height="1.88" /><rect
					x="679.79"
					y="522.63"
					width="66.835"
					height="1.878"
				/><rect x="342.79" y="452.64" width="101.59" height="1.879" /><rect
					x="342.79"
					y="446.62"
					width="66.835"
					height="1.878"
				/><rect x="625.77" y="856.37" width="3.388" height="3.653" /><rect
					x="617.76"
					y="856.37"
					width="3.389"
					height="3.653"
				/><rect x="609.74" y="856.37" width="3.388" height="3.653" /><rect
					x="601.73"
					y="856.37"
					width="3.386"
					height="3.653"
				/><rect x="593.72" y="856.37" width="3.385" height="3.653" /><rect
					x="585.71"
					y="856.37"
					width="3.387"
					height="3.653"
				/><rect x="577.69" y="856.37" width="3.387" height="3.653" /><rect
					x="569.68"
					y="856.37"
					width="3.386"
					height="3.653"
				/><rect x="561.67" y="856.37" width="3.387" height="3.653" /><rect
					x="553.66"
					y="856.37"
					width="3.385"
					height="3.653"
				/><rect x="545.64" y="856.37" width="3.385" height="3.653" /><rect
					x="537.63"
					y="856.37"
					width="3.383"
					height="3.653"
				/><rect x="529.62" y="856.37" width="3.386" height="3.653" /><rect
					x="746.36"
					y="816.23"
					width="3.388"
					height="3.654"
				/><rect x="738.35" y="816.23" width="3.389" height="3.654" /><rect
					x="730.33"
					y="816.23"
					width="3.388"
					height="3.654"
				/><rect x="722.32" y="816.23" width="3.386" height="3.654" /><rect
					x="714.31"
					y="816.23"
					width="3.386"
					height="3.654"
				/><rect x="706.3" y="816.23" width="3.386" height="3.654" /><rect
					x="698.28"
					y="816.23"
					width="3.389"
					height="3.654"
				/><rect x="690.27" y="816.23" width="3.386" height="3.654" /><rect
					x="682.26"
					y="816.23"
					width="3.389"
					height="3.654"
				/><rect x="674.24" y="816.23" width="3.386" height="3.654" /><rect
					x="666.23"
					y="816.23"
					width="3.386"
					height="3.654"
				/><rect x="658.22" y="816.23" width="3.383" height="3.654" /><rect
					x="650.21"
					y="816.23"
					width="3.386"
					height="3.654"
				/><rect x="844.31" y="696.42" width="2.995" height="3.478" /><rect
					x="837.22"
					y="696.42"
					width="2.993"
					height="3.478"
				/><rect x="830.14" y="696.42" width="2.994" height="3.478" /><rect
					x="823.05"
					y="696.42"
					width="2.997"
					height="3.478"
				/><rect x="815.96" y="696.42" width="2.994" height="3.478" /><rect
					x="808.87"
					y="696.42"
					width="2.995"
					height="3.478"
				/><rect x="801.78" y="696.42" width="2.998" height="3.478" /><rect
					x="794.7"
					y="696.42"
					width="2.993"
					height="3.478"
				/><rect x="787.61" y="696.42" width="2.994" height="3.478" /><rect
					x="780.52"
					y="696.42"
					width="2.998"
					height="3.478"
				/><rect x="773.44" y="696.42" width="2.994" height="3.478" /><rect
					x="766.35"
					y="696.42"
					width="2.991"
					height="3.478"
				/><rect x="759.26" y="696.42" width="2.995" height="3.478" /><rect
					x="647.43"
					y="431.48"
					width="3.887"
					height="4.514"
				/><rect x="638.23" y="431.48" width="3.882" height="4.514" /><rect
					x="629.04"
					y="431.48"
					width="3.885"
					height="4.514"
				/><rect x="619.85" y="431.48" width="3.887" height="4.514" /><rect
					x="610.66"
					y="431.48"
					width="3.883"
					height="4.514"
				/><rect x="601.46" y="431.48" width="3.886" height="4.514" /><rect
					x="592.27"
					y="431.48"
					width="3.888"
					height="4.514"
				/><rect x="583.08" y="431.48" width="3.883" height="4.514" /><rect
					x="573.88"
					y="431.48"
					width="3.884"
					height="4.514"
				/><rect x="564.69" y="431.48" width="3.889" height="4.514" /><rect
					x="555.5"
					y="431.48"
					width="3.883"
					height="4.514"
				/><rect x="546.31" y="431.48" width="3.88" height="4.514" /><rect
					x="537.11"
					y="431.48"
					width="3.885"
					height="4.514"
				/><rect x="760.47" y="483.7" width="3.885" height="4.515" /><rect
					x="751.28"
					y="483.7"
					width="3.881"
					height="4.515"
				/><rect x="742.09" y="483.7" width="3.884" height="4.515" /><rect
					x="732.89"
					y="483.7"
					width="3.888"
					height="4.515"
				/><rect x="723.7" y="483.7" width="3.884" height="4.515" /><rect
					x="714.5"
					y="483.7"
					width="3.886"
					height="4.515"
				/><rect x="705.31" y="483.7" width="3.888" height="4.515" /><rect
					x="696.12"
					y="483.7"
					width="3.882"
					height="4.515"
				/><rect x="686.92" y="483.7" width="3.885" height="4.515" /><rect
					x="677.73"
					y="483.7"
					width="3.89"
					height="4.515"
				/><rect x="668.54" y="483.7" width="3.883" height="4.515" /><rect
					x="659.35"
					y="483.7"
					width="3.88"
					height="4.515"
				/><rect x="650.15" y="483.7" width="3.885" height="4.515" /><rect
					x="919.85"
					y="675.04"
					width="3.886"
					height="4.516"
				/><rect x="910.66" y="675.04" width="3.882" height="4.516" /><rect
					x="901.47"
					y="675.04"
					width="3.885"
					height="4.516"
				/><rect x="892.28" y="675.04" width="3.887" height="4.516" /><rect
					x="883.09"
					y="675.04"
					width="3.882"
					height="4.516"
				/><rect x="873.89" y="675.04" width="3.885" height="4.516" /><rect
					x="864.7"
					y="675.04"
					width="3.888"
					height="4.516"
				/><rect x="855.5" y="675.04" width="3.883" height="4.516" /><rect
					x="846.31"
					y="675.04"
					width="3.885"
					height="4.516"
				/><rect x="837.11" y="675.04" width="3.889" height="4.516" /><rect
					x="827.93"
					y="675.04"
					width="3.883"
					height="4.516"
				/><rect x="818.73" y="675.04" width="3.88" height="4.516" /><rect
					x="809.54"
					y="675.04"
					width="3.886"
					height="4.516"
				/><path
					d="m564.25 831.64c0 0.186-0.011 0.341-0.03 0.467-0.022 0.129-0.05 0.228-0.09 0.307-0.041 0.076-0.086 0.131-0.14 0.167-0.054 0.029-0.109 0.046-0.169 0.046h-3.107v3.385c0 0.069-0.018 0.126-0.049 0.176-0.036 0.052-0.09 0.093-0.171 0.128-0.081 0.042-0.186 0.068-0.32 0.088-0.132 0.019-0.298 0.03-0.499 0.03-0.199 0-0.366-0.012-0.498-0.03-0.134-0.02-0.24-0.046-0.319-0.088-0.081-0.035-0.14-0.076-0.176-0.128-0.036-0.05-0.054-0.107-0.054-0.176v-3.385h-3.097c-0.058 0-0.113-0.017-0.164-0.046-0.05-0.036-0.096-0.091-0.134-0.167-0.041-0.079-0.074-0.178-0.096-0.307-0.024-0.126-0.036-0.281-0.036-0.467 0-0.18 0.011-0.336 0.03-0.467 0.019-0.13 0.048-0.233 0.083-0.31 0.038-0.073 0.081-0.131 0.127-0.164 0.045-0.032 0.099-0.049 0.158-0.049h3.127v-3.374c0-0.071 0.018-0.129 0.054-0.189 0.037-0.055 0.096-0.102 0.176-0.136 0.079-0.039 0.185-0.069 0.319-0.085 0.133-0.019 0.3-0.031 0.498-0.031 0.201 0 0.367 0.012 0.499 0.031 0.134 0.016 0.239 0.046 0.32 0.085 0.081 0.034 0.135 0.081 0.171 0.136 0.031 0.06 0.049 0.118 0.049 0.189v3.374h3.135c0.053 0 0.105 0.017 0.156 0.049 0.05 0.033 0.094 0.091 0.129 0.164 0.036 0.076 0.063 0.18 0.085 0.31 0.022 0.131 0.033 0.287 0.033 0.467z"
				/><path
					d="m408.82 583.31c0 0.186-9e-3 0.341-0.028 0.467-0.022 0.128-0.052 0.227-0.093 0.306-0.039 0.078-0.085 0.131-0.138 0.167-0.053 0.031-0.111 0.047-0.169 0.047h-3.107v3.386c0 0.068-0.018 0.126-0.05 0.175-0.033 0.053-0.09 0.093-0.169 0.129-0.081 0.04-0.186 0.068-0.32 0.087-0.133 0.02-0.298 0.031-0.5 0.031-0.198 0-0.365-0.011-0.498-0.031-0.134-0.019-0.24-0.046-0.32-0.087-0.08-0.036-0.139-0.076-0.176-0.129-0.037-0.049-0.053-0.107-0.053-0.175v-3.386h-3.099c-0.058 0-0.112-0.016-0.163-0.047-0.05-0.035-0.095-0.089-0.133-0.167-0.042-0.079-0.074-0.177-0.096-0.306-0.024-0.126-0.036-0.281-0.036-0.467 0-0.181 0.011-0.336 0.032-0.467 0.018-0.129 0.046-0.232 0.082-0.308 0.038-0.074 0.079-0.132 0.125-0.165 0.047-0.033 0.101-0.049 0.16-0.049h3.127v-3.374c0-0.071 0.017-0.129 0.053-0.189 0.037-0.055 0.096-0.101 0.176-0.137 0.079-0.038 0.186-0.068 0.32-0.084 0.133-0.02 0.299-0.03 0.498-0.03 0.202 0 0.367 0.011 0.5 0.03 0.134 0.016 0.239 0.047 0.32 0.084 0.079 0.036 0.136 0.082 0.169 0.137 0.032 0.06 0.05 0.118 0.05 0.189v3.374h3.136c0.053 0 0.104 0.016 0.156 0.049 0.049 0.033 0.094 0.09 0.128 0.165 0.037 0.076 0.065 0.18 0.087 0.308 0.021 0.131 0.029 0.286 0.029 0.467z"
				/><path
					d="m671.26 412.87c0 0.186-0.011 0.342-0.03 0.469-0.021 0.127-0.051 0.227-0.092 0.306-0.04 0.076-0.085 0.129-0.139 0.165-0.054 0.032-0.11 0.048-0.169 0.048h-3.106v3.385c0 0.069-0.019 0.127-0.051 0.176-0.033 0.05-0.091 0.093-0.17 0.128-0.08 0.039-0.186 0.068-0.319 0.087-0.132 0.019-0.298 0.03-0.5 0.03-0.198 0-0.365-0.011-0.497-0.03-0.135-0.02-0.241-0.048-0.32-0.087-0.08-0.036-0.139-0.078-0.176-0.128-0.037-0.049-0.054-0.107-0.054-0.176v-3.385h-3.099c-0.058 0-0.112-0.016-0.163-0.048-0.05-0.035-0.096-0.089-0.133-0.165-0.042-0.08-0.074-0.179-0.097-0.306-0.024-0.127-0.034-0.283-0.034-0.469 0-0.18 0.01-0.335 0.03-0.466 0.019-0.128 0.047-0.232 0.082-0.309 0.039-0.075 0.079-0.131 0.126-0.165 0.047-0.033 0.101-0.049 0.159-0.049h3.128v-3.375c0-0.069 0.017-0.129 0.054-0.187 0.037-0.057 0.096-0.103 0.176-0.137 0.079-0.039 0.186-0.069 0.32-0.086 0.132-0.019 0.299-0.03 0.497-0.03 0.202 0 0.368 0.011 0.5 0.03 0.134 0.018 0.239 0.047 0.319 0.086 0.079 0.034 0.137 0.08 0.17 0.137 0.032 0.058 0.051 0.117 0.051 0.187v3.375h3.135c0.054 0 0.104 0.016 0.156 0.049 0.049 0.034 0.095 0.09 0.128 0.165 0.037 0.077 0.066 0.18 0.087 0.309 0.02 0.131 0.031 0.286 0.031 0.466z"
				/><path
					d="m503.85 398.5c0.295-0.292 0.587-0.581 0.885-0.866-0.185 0.179-0.429 0.419-0.885 0.866z"
					fill="#fff"
				/><path
					d="m602.11 483.1 0.015-0.02c-9e-3 8e-3 -0.019 0.018-0.024 0.026l-2e-3 2e-3c2e-3 -1e-3 4e-3 -1e-3 0.011-8e-3z"
					fill="#fff"
				/><rect x="265.35" y="673.16" width="117.43" height="2.178" /><rect
					x="265.35"
					y="666.2"
					width="77.251"
					height="2.175"
				/><path
					d="m460.22 804.28c1.441-4.596 3.755-8.968 6.98-12.835l-0.044 0.044-4.358-8.889 7.879-6.41 7.816 6.071-0.051 0.042c4.424-2.359 9.179-3.758 13.976-4.209l3.217-9.334 10.086 1.035 1.23 9.776c4.607 1.414 8.997 3.744 12.851 6.92l8.837-4.337 6.425 7.889-6.054 7.777c2.355 4.424 3.732 9.17 4.193 13.984l9.31 3.181-1.026 10.113-9.783 1.227c-1.411 4.61-3.731 8.998-6.928 12.857l4.323 8.828-7.879 6.406-7.755-6.031c-4.432 2.347-9.203 3.724-14.004 4.17l-3.207 9.342-10.101-1.037-1.221-9.813c-4.61-1.41-8.984-3.752-12.83-6.93l-8.863 4.351-6.417-7.884 6.067-7.796c-2.334-4.412-3.7-9.173-4.152-13.96l-9.353-3.206 1.027-10.105zm46.496 2.293c-4.837-5.943-13.56-6.826-19.501-1.992-5.944 4.837-6.841 13.545-2.007 19.491 4.832 5.943 13.567 6.851 19.505 2.022 5.944-4.834 6.846-13.58 2.003-19.521z"
					fill="#fff"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
					><path
						d="m514.28 835.07c-10.917 10.351-28.155 9.891-38.504-1.023-10.349-10.917-9.892-28.153 1.022-38.505"
					/><path d="m520.16 826.96c-0.726 1.53-1.596 2.994-2.599 4.363" /><path
						d="m482.18 800.94c8.206-7.782 21.162-7.436 28.943 0.768 7.778 8.203 7.435 21.161-0.768 28.94"
					/><path d="m477.76 807.03c0.543-1.15 1.201-2.249 1.954-3.275" /></g
				><path
					d="m351.24 741.03c4.256-7.115 9.885-13.51 16.837-18.688l-0.09 0.057-3.729-16.633 15.762-7.566 10.65 13.299-0.101 0.047c8.351-2.17 16.874-2.609 25.085-1.437l9.132-14.338 16.471 5.781-1.865 16.863c7.149 4.216 13.562 9.877 18.738 16.739l16.538-3.716 7.588 15.788-13.252 10.589c2.17 8.351 2.568 16.849 1.407 25.096l14.309 9.061-5.774 16.518-16.87-1.872c-4.212 7.151-9.861 13.57-16.761 18.745l3.699 16.516-15.763 7.564-10.564-13.21c-8.361 2.151-16.902 2.545-25.119 1.364l-9.118 14.352-16.492-5.788 1.892-16.922c-7.152-4.211-13.534-9.884-18.699-16.745l-16.581 3.722-7.58-15.77 13.284-10.621c-2.134-8.32-2.516-16.839-1.35-25.035l-14.373-9.116 5.775-16.51zm76.925 22.491c-5.714-11.89-19.964-16.862-31.85-11.159-11.892 5.711-16.89 19.936-11.183 31.828 5.707 11.886 19.965 16.909 31.846 11.212 11.889-5.706 16.907-19.992 11.187-31.881z"
					fill="#fff"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
					><path
						d="m429.4 814.28c-22.43 12.949-51.103 5.262-64.05-17.161-12.948-22.426-5.264-51.099 17.161-64.048"
					/><path d="m442.49 803.07c-1.827 2.271-3.872 4.368-6.099 6.257" /><path
						d="m389.35 744.25c16.859-9.733 38.411-3.958 48.145 12.896 9.732 16.856 3.958 38.408-12.896 48.145"
					/><path d="m379.51 752.68c1.373-1.705 2.91-3.284 4.585-4.702" /></g
				><g stroke-width="2.5016"
					><polygon
						points="592.65 470.22 614.11 470.22 603.14 497.88"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m603.14 499.32h-0.011c-0.599-4e-3 -1.132-0.375-1.345-0.934l-10.484-27.653c-0.167-0.445-0.106-0.944 0.164-1.336s0.716-0.625 1.191-0.625h21.456c0.478 0 0.926 0.238 1.196 0.635 0.268 0.397 0.325 0.902 0.147 1.347l-10.97 27.652c-0.218 0.552-0.752 0.914-1.344 0.914zm-8.389-27.652 8.419 22.202 8.807-22.202z"
					/><polygon
						points="603.14 457.06 613.63 469.94 592.17 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m613.65 471.38h-0.021-21.456c-0.563 0-1.077-0.328-1.314-0.841-0.235-0.512-0.153-1.115 0.212-1.546l10.961-12.871c0.278-0.327 0.652-0.534 1.117-0.509 0.433 5e-3 0.837 0.2 1.106 0.533l10.359 12.706c0.298 0.265 0.484 0.65 0.484 1.079 2e-3 0.801-0.647 1.449-1.448 1.449zm-18.34-2.895h15.27l-7.468-9.162z"
					/><polygon
						points="581.68 457.06 592.17 469.94 570.72 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m592.2 471.38h-0.025-21.456c-0.566 0-1.08-0.328-1.315-0.841-0.238-0.512-0.156-1.115 0.21-1.546l10.966-12.871c0.278-0.327 0.644-0.534 1.12-0.509 0.429 5e-3 0.833 0.2 1.104 0.533l10.359 12.706c0.296 0.265 0.484 0.65 0.484 1.079 1e-3 0.801-0.647 1.449-1.447 1.449zm-18.346-2.895h15.275l-7.468-9.162z"
					/><polygon
						points="624.59 457.06 635.08 469.94 613.63 469.94"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m635.11 471.38h-0.021-21.456c-0.565 0-1.079-0.328-1.314-0.841-0.237-0.512-0.153-1.115 0.211-1.546l10.968-12.871c0.278-0.327 0.653-0.534 1.118-0.509 0.429 5e-3 0.833 0.2 1.106 0.534l10.354 12.706c0.297 0.265 0.483 0.65 0.483 1.079 0 0.8-0.648 1.448-1.449 1.448zm-18.343-2.895h15.274l-7.468-9.162z"
					/><polygon
						points="592.17 469.94 581.68 457.06 603.14 457.06"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m592.17 471.38h-0.014c-0.429-4e-3 -0.836-0.2-1.107-0.532l-10.493-12.871c-0.352-0.434-0.423-1.031-0.186-1.535 0.24-0.506 0.748-0.828 1.309-0.828h21.453c0.563 0 1.076 0.328 1.315 0.841 0.237 0.512 0.153 1.116-0.214 1.545l-10.96 12.87c-0.275 0.325-0.677 0.51-1.103 0.51zm-7.444-12.87 7.468 9.161 7.804-9.161z"
					/><polygon
						points="613.63 469.94 603.14 457.06 624.59 457.06"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m613.63 471.38h-0.017c-0.43-4e-3 -0.833-0.2-1.106-0.532l-10.493-12.871c-0.353-0.433-0.424-1.031-0.186-1.535 0.24-0.506 0.748-0.828 1.309-0.828h21.458c0.563 0 1.078 0.328 1.315 0.841 0.237 0.512 0.152 1.116-0.214 1.545l-10.966 12.87c-0.275 0.325-0.676 0.51-1.1 0.51zm-7.446-12.87 7.471 9.161 7.807-9.161z"
					/><polygon
						points="571.2 470.22 592.65 470.22 603.14 497.88"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m603.14 499.32c-0.339 0-0.677-0.119-0.948-0.353l-31.94-27.652c-0.457-0.395-0.621-1.034-0.41-1.6 0.213-0.567 0.754-0.943 1.357-0.943h21.456c0.601 0 1.14 0.372 1.353 0.934l10.4 27.426c0.128 0.216 0.202 0.47 0.202 0.74 0 0.8-0.648 1.448-1.449 1.448h-0.021zm-28.058-27.652 24.672 21.358-8.099-21.358z"
					/><polygon
						points="635.08 470.22 613.63 470.22 603.17 497.85"
						clip-rule="evenodd"
						fill="#fff"
						fill-rule="evenodd"
					/><path
						d="m603.17 499.3c-0.29 0-0.579-0.086-0.828-0.261-0.543-0.379-0.76-1.08-0.524-1.7l10.46-27.628c0.213-0.563 0.754-0.935 1.356-0.935h21.456c0.603 0 1.144 0.376 1.354 0.943 0.211 0.566 0.05 1.204-0.407 1.6l-31.919 27.628c-0.27 0.234-0.609 0.353-0.948 0.353zm11.463-27.628-8.08 21.337 24.649-21.337z"
					/></g
				><polygon
					points="583.66 824.35 582.4 831.73 588 824.35 600.88 824.35 600.88 802.67 578.09 802.67 578.09 824.35"
					fill="#fff"
				/><path
					d="m588.36 816.74c-0.313 0-0.611-0.129-0.827-0.355l-1.868-1.953c-0.432-0.456-0.413-1.175 0.041-1.609 0.456-0.432 1.174-0.419 1.607 0.035l0.979 1.029 3.302-4.023c0.397-0.483 1.113-0.558 1.599-0.159 0.487 0.399 0.556 1.115 0.158 1.602l-4.115 5.017c-0.206 0.254-0.512 0.404-0.833 0.412-0.016 4e-3 -0.031 4e-3 -0.043 4e-3z"
					stroke-width="2.5016"
				/><polygon
					points="461.51 555.58 460.25 562.96 465.85 555.58 478.74 555.58 478.74 533.9 455.94 533.9 455.94 555.58"
					fill="#fff"
				/><path
					d="m466.22 547.98c-0.313 0-0.611-0.131-0.827-0.355l-1.868-1.956c-0.431-0.455-0.413-1.174 0.041-1.608 0.456-0.432 1.173-0.417 1.607 0.037l0.979 1.028 3.302-4.022c0.397-0.487 1.113-0.558 1.598-0.158 0.488 0.395 0.556 1.114 0.159 1.598l-4.115 5.019c-0.206 0.251-0.513 0.402-0.833 0.412-0.016 5e-3 -0.031 5e-3 -0.043 5e-3z"
				/><path
					d="m572.41 770.18-9.883 6.87c-0.314 0.043-0.609 0.21-0.806 0.491-0.159 0.229-0.219 0.491-0.202 0.751-0.017 0.257 0.044 0.522 0.202 0.752 0.197 0.281 0.492 0.447 0.806 0.489l9.883 6.872c0.539 0.371 1.273 0.237 1.643-0.295 0.368-0.536 0.24-1.272-0.295-1.64l-8.889-6.179 8.889-6.178c0.535-0.372 0.663-1.104 0.295-1.641-0.369-0.529-1.104-0.661-1.643-0.292z"
				/><path
					d="m582.99 770.18-9.884 6.87c-0.314 0.043-0.612 0.21-0.806 0.491-0.162 0.229-0.221 0.491-0.205 0.751-0.016 0.257 0.044 0.522 0.205 0.752 0.194 0.281 0.492 0.447 0.806 0.489l9.884 6.872c0.536 0.371 1.268 0.237 1.64-0.295 0.372-0.536 0.241-1.272-0.292-1.64l-8.894-6.179 8.894-6.178c0.533-0.372 0.664-1.104 0.292-1.641-0.373-0.529-1.105-0.661-1.64-0.292z"
				/><path
					d="m593.56 769.72-9.881 6.873c-0.317 0.04-0.612 0.21-0.806 0.488-0.161 0.229-0.222 0.492-0.205 0.752-0.017 0.26 0.044 0.522 0.205 0.751 0.194 0.282 0.489 0.449 0.806 0.492l9.881 6.87c0.538 0.371 1.273 0.239 1.643-0.296 0.371-0.533 0.24-1.268-0.296-1.64l-8.891-6.178 8.891-6.179c0.536-0.372 0.667-1.104 0.296-1.639-0.37-0.535-1.105-0.663-1.643-0.294z"
				/><path
					d="m604.14 769.72-9.885 6.873c-0.314 0.04-0.609 0.21-0.803 0.488-0.159 0.229-0.221 0.492-0.203 0.752-0.019 0.26 0.043 0.522 0.203 0.751 0.194 0.282 0.489 0.449 0.803 0.492l9.885 6.87c0.536 0.371 1.271 0.239 1.644-0.296 0.368-0.533 0.237-1.268-0.299-1.64l-8.888-6.178 8.888-6.179c0.536-0.372 0.667-1.104 0.299-1.639-0.373-0.535-1.108-0.663-1.644-0.294z"
				/><path
					d="m777.09 785.21-9.884 6.872c-0.314 0.041-0.609 0.21-0.807 0.489-0.158 0.229-0.218 0.494-0.202 0.751-0.016 0.261 0.044 0.522 0.202 0.752 0.197 0.281 0.493 0.447 0.807 0.489l9.884 6.872c0.538 0.371 1.273 0.24 1.642-0.295 0.369-0.533 0.241-1.268-0.294-1.637l-8.89-6.182 8.89-6.178c0.535-0.372 0.663-1.103 0.294-1.64-0.369-0.53-1.104-0.662-1.642-0.293z"
				/><path
					d="m787.67 785.21-9.884 6.872c-0.313 0.041-0.611 0.21-0.805 0.489-0.162 0.229-0.222 0.494-0.206 0.751-0.016 0.261 0.044 0.522 0.206 0.752 0.193 0.281 0.491 0.447 0.805 0.489l9.884 6.872c0.536 0.371 1.269 0.24 1.64-0.295 0.372-0.533 0.241-1.268-0.292-1.637l-8.895-6.182 8.895-6.178c0.533-0.372 0.664-1.103 0.292-1.64-0.371-0.53-1.104-0.662-1.64-0.293z"
				/><path
					d="m798.24 784.76-9.881 6.873c-0.316 0.044-0.612 0.21-0.807 0.488-0.16 0.229-0.221 0.494-0.205 0.755-0.016 0.257 0.045 0.518 0.205 0.751 0.194 0.278 0.49 0.446 0.807 0.489l9.881 6.87c0.538 0.374 1.273 0.239 1.643-0.292 0.372-0.536 0.24-1.271-0.295-1.643l-8.892-6.175 8.892-6.182c0.535-0.368 0.667-1.103 0.295-1.637-0.369-0.534-1.105-0.665-1.643-0.297z"
				/><path
					d="m808.82 784.76-9.887 6.873c-0.313 0.044-0.609 0.21-0.804 0.488-0.158 0.229-0.221 0.494-0.201 0.755-0.019 0.257 0.043 0.518 0.201 0.751 0.194 0.278 0.49 0.446 0.804 0.489l9.887 6.87c0.535 0.374 1.271 0.239 1.642-0.292 0.369-0.536 0.238-1.271-0.297-1.643l-8.89-6.175 8.89-6.182c0.535-0.368 0.666-1.103 0.297-1.637-0.371-0.534-1.107-0.665-1.642-0.297z"
				/><path
					d="m521.44 519.92-9.883 6.872c-0.314 0.042-0.609 0.21-0.806 0.489-0.159 0.229-0.219 0.495-0.203 0.753-0.016 0.259 0.044 0.52 0.203 0.751 0.197 0.28 0.492 0.449 0.806 0.489l9.883 6.871c0.539 0.373 1.273 0.24 1.642-0.295 0.369-0.533 0.241-1.268-0.295-1.637l-8.889-6.18 8.889-6.18c0.536-0.37 0.664-1.103 0.295-1.638-0.369-0.532-1.104-0.664-1.642-0.295z"
				/><path
					d="m532.02 519.92-9.884 6.872c-0.315 0.042-0.612 0.21-0.806 0.489-0.161 0.229-0.222 0.495-0.205 0.753-0.017 0.259 0.044 0.52 0.205 0.751 0.194 0.28 0.492 0.449 0.806 0.489l9.884 6.871c0.535 0.373 1.268 0.24 1.639-0.295 0.372-0.533 0.24-1.268-0.292-1.637l-8.895-6.18 8.895-6.18c0.533-0.37 0.664-1.103 0.292-1.638-0.371-0.532-1.104-0.664-1.639-0.295z"
				/><path
					d="m542.59 519.47-9.881 6.871c-0.317 0.044-0.612 0.211-0.806 0.489-0.162 0.231-0.222 0.494-0.205 0.754-0.017 0.257 0.044 0.521 0.205 0.751 0.194 0.28 0.489 0.445 0.806 0.489l9.881 6.871c0.538 0.373 1.273 0.239 1.642-0.294 0.372-0.535 0.241-1.27-0.295-1.64l-8.892-6.177 8.892-6.18c0.536-0.37 0.667-1.105 0.295-1.638-0.369-0.535-1.104-0.665-1.642-0.296z"
				/><path
					d="m553.17 519.47-9.886 6.871c-0.314 0.044-0.609 0.211-0.803 0.489-0.159 0.231-0.222 0.494-0.202 0.754-0.019 0.257 0.043 0.521 0.202 0.751 0.194 0.28 0.489 0.445 0.803 0.489l9.886 6.871c0.536 0.373 1.271 0.239 1.642-0.294 0.369-0.535 0.238-1.27-0.298-1.64l-8.889-6.177 8.889-6.18c0.536-0.37 0.667-1.105 0.298-1.638-0.371-0.535-1.106-0.665-1.642-0.296z"
				/><rect x="563.04" y="704.74" width="38.091" height="2.306" /><rect
					x="514.23"
					y="704.74"
					width="38.092"
					height="2.306"
				/><rect x="503.52" y="704.74" width="3.571" height="2.306" /><rect
					x="307.35"
					y="587.22"
					width="73.093"
					height="2.306"
				/><rect x="213.69" y="587.22" width="73.09" height="2.306" /><rect
					x="193.14"
					y="587.22"
					width="6.855"
					height="2.306"
				/></g
			><path
				d="m811.81 738.74c0.759-1.984 1.177-4.137 1.177-6.386 0-9.913-8.032-17.944-17.947-17.944-8.04 0-14.843 5.287-17.121 12.58-2.123-2.992-5.613-4.946-9.562-4.946-6.473 0-11.717 5.247-11.717 11.715 0 1.691 0.362 3.298 1.009 4.752h-6.552c-4.421 0-8.008 3.582-8.008 8.01 0 4.415 3.587 8.003 8.008 8.003h58.806c4.422 0 8.005-3.588 8.005-8.003-1e-3 -3.766-2.597-6.923-6.098-7.781z"
				fill="#f69823"
			/></g
		><path
			d="m775.66 747.82c-0.624-1.631-0.968-3.399-0.968-5.249 0-8.151 6.604-14.753 14.756-14.753 6.609 0 12.204 4.347 14.075 10.343 1.746-2.46 4.615-4.066 7.861-4.066 5.32 0 9.633 4.312 9.633 9.63 0 1.391-0.298 2.71-0.829 3.907h5.387c3.634 0 6.583 2.946 6.583 6.583 0 3.631-2.949 6.582-6.583 6.582h-48.347c-3.634 0-6.58-2.951-6.58-6.582 0-3.094 2.134-5.69 5.012-6.395z"
			fill="#fff"
			stroke="#000"
			stroke-miterlimit="10"
			stroke-width="7.5046"
		/><g stroke-width="2.5016"
			><path
				d="m283.82 614.78-1.765-6e-3c-1.35-0.013-2.463 1.554-2.481 3.502l-0.043 4.979c-0.016 1.95 1.068 3.541 2.423 3.557l1.866 7e-3z"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="5.0031"
			/><g stroke-width="2.5016"
				><g stroke="#000" stroke-width="5.0031"
					><polygon
						points="379.34 626.9 391.73 620.93 379.34 614.7"
						fill="none"
						stroke-linecap="round"
					/><polygon
						points="391.73 620.97 388.47 619.26 388.44 622.62"
						fill="#231f20"
						stroke-miterlimit="10"
					/><rect
						x="293.26"
						y="614.18"
						width="84.981"
						height="13.242"
						fill="#f59121"
						stroke-linecap="round"
					/></g
				><rect x="293.83" y="620.21" width="84.7" height="1.182" stroke-width="2.5016" /><rect
					x="285.9"
					y="613.45"
					width="5.122"
					height="14.697"
					fill="#fff"
				/><path
					d="m628.61 396.42c0-6.367 0.113-9.46 0.113-12.828h-12.2c2.523 5.95-1.082 8.911-3.993 8.911-2.707 0-6.212-2.961-3.688-8.911h-12.199c0 3.368 0.111 6.461 0.111 12.828-11.194-7.039-12.323 13.361 0 6.979 0 5.354 0.137 5.953 0.137 12.83h31.584c0-6.877 0.136-7.475 0.136-12.83 12.323 6.382 11.196-14.018-1e-3 -6.979z"
					clip-rule="evenodd"
					fill="#fff"
					fill-rule="evenodd"
					stroke-width="2.5016"
				/><path
					d="m614.88 377.26c0.134 0.051 0.261 0.09 0.398 0.147l-0.033-12.479c-0.094 0-12.975 0.056-13.15 0.056 7.233-11.507-13.73-12.665-7.172 0-0.181 0-13.272-0.056-13.272-0.056 0 1.118 0.088 12.612 0.088 12.612-11.001-6.421-12.082 13.417 0 7.586v13.229h33.54v-13.053c-0.138 0.057-0.265 0.095-0.4 0.147-5.842 2.262-8.758-1.327-8.758-4.253-1e-3 -2.719 2.915-6.205 8.759-3.936z"
					fill="#fff"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="6.2539"
				/><polygon points="642.46 397.74 655.03 398.27 641.93 385.17" stroke-width="2.5016" /><g
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
					><path
						d="m597.85 342.91c14.124-13.397 36.43-12.802 49.824 1.321 13.393 14.123 12.799 36.431-1.322 49.823"
					/><path d="m590.24 353.39c0.938-1.98 2.066-3.872 3.364-5.644" /></g
				><rect
					x="687.07"
					y="450.16"
					width="83.272"
					height="2.738"
					fill="#231f20"
					stroke-width="2.5016"
				/><rect
					x="715.56"
					y="458.92"
					width="54.785"
					height="2.735"
					fill="#231f20"
					stroke-width="2.5016"
				/><path
					d="m785.51 377.29c-35.702 0-66.191 17.513-78.268 42.179 12.076 24.671 42.565 42.188 78.268 42.188s66.19-17.517 78.267-42.188c-12.078-24.666-42.564-42.179-78.267-42.179z"
					fill="#fff"
					stroke-width="2.5016"
				/><g stroke="#000" stroke-width="7.5046"
					><path
						d="m745.87 419.47c0-21.886 17.746-39.637 39.637-39.637 21.896 0 39.64 17.751 39.64 39.637 0 21.894-17.744 39.641-39.64 39.641-21.888 0-39.637-17.748-39.637-39.641z"
						fill="#fff"
					/><path
						d="m785.51 377.29c-35.702 0-66.191 17.513-78.268 42.179 12.076 24.671 42.565 42.188 78.268 42.188s66.19-17.517 78.267-42.188c-12.078-24.666-42.564-42.179-78.267-42.179z"
						fill="none"
						stroke-miterlimit="10"
					/><path
						d="m824.15 384.75c-10.824-3.361-21.527-5.957-34.021-5.386-35.665 1.624-66.454 21.745-77.395 46.934"
						fill="none"
						stroke-miterlimit="10"
					/></g
				><path
					d="m796.67 400.55-11.166 18.919v-21.969c-12.131 0-21.972 9.838-21.972 21.969 0 12.138 9.841 21.973 21.972 21.973 12.135 0 21.975-9.835 21.975-21.973-1e-3 -8.058-4.346-15.097-10.809-18.919z"
					fill="#f59121"
					stroke-width="2.5016"
				/><path
					d="m799.51 443.72c-13.393 7.734-30.518 3.148-38.251-10.25-7.731-13.39-3.143-30.516 10.253-38.253"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/><path
					d="m807.33 437.02c-1.095 1.363-2.313 2.621-3.644 3.741"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/><path
					d="m794.93 419.48c0 0.257-0.014 0.473-0.041 0.648-0.03 0.178-0.07 0.317-0.126 0.425-0.057 0.107-0.117 0.182-0.192 0.23-0.075 0.042-0.151 0.068-0.235 0.068h-4.302v4.688c0 0.093-0.024 0.174-0.071 0.242-0.046 0.069-0.123 0.13-0.234 0.179-0.112 0.054-0.257 0.093-0.442 0.122-0.184 0.024-0.413 0.04-0.692 0.04-0.276 0-0.506-0.016-0.691-0.04-0.183-0.028-0.33-0.068-0.44-0.122-0.11-0.049-0.193-0.109-0.245-0.179-0.049-0.068-0.072-0.149-0.072-0.242v-4.688h-4.291c-0.079 0-0.156-0.026-0.225-0.068-0.071-0.048-0.134-0.122-0.187-0.23-0.057-0.108-0.103-0.248-0.133-0.425-0.036-0.175-0.049-0.391-0.049-0.648 0-0.251 0.013-0.461 0.041-0.645 0.026-0.179 0.067-0.321 0.115-0.426 0.054-0.106 0.11-0.183 0.176-0.231 0.063-0.045 0.138-0.067 0.222-0.067h4.33v-4.675c0-0.096 0.024-0.178 0.072-0.259 0.052-0.075 0.135-0.141 0.245-0.189 0.11-0.055 0.258-0.094 0.44-0.12 0.186-0.025 0.415-0.04 0.691-0.04 0.279 0 0.509 0.015 0.692 0.04 0.186 0.026 0.33 0.065 0.442 0.12 0.111 0.048 0.189 0.114 0.234 0.189 0.047 0.082 0.071 0.164 0.071 0.259v4.675h4.342c0.074 0 0.146 0.022 0.217 0.067 0.067 0.048 0.131 0.125 0.179 0.231 0.051 0.105 0.088 0.248 0.118 0.426 0.027 0.184 0.041 0.394 0.041 0.645z"
					stroke-width="2.5016"
				/></g
			><path
				d="m549.33 450.01c0 28.15-22.819 50.962-50.954 50.962-28.153 0-50.962-22.812-50.962-50.962 0-28.119 22.809-50.938 50.962-50.938 28.134 1e-3 50.954 22.82 50.954 50.938z"
				fill="#f69823"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/><g stroke-width="2.5016"
				><path
					d="m538.21 450.01c0 22.011-17.832 39.834-39.834 39.834-21.986 0-39.816-17.823-39.816-39.834 0-21.974 17.829-39.8 39.816-39.8 22.002 1e-3 39.834 17.826 39.834 39.8z"
					fill="#fff"
				/><path
					d="m525.89 450.01c0 15.22-12.31 27.531-27.514 27.531s-27.525-12.311-27.525-27.531c0-15.171 12.321-27.507 27.525-27.507s27.514 12.336 27.514 27.507z"
					fill="#f69823"
				/><path
					d="m512.11 450.01c0 7.588-6.154 13.741-13.734 13.741s-13.72-6.152-13.72-13.741c0-7.562 6.14-13.706 13.72-13.706s13.734 6.144 13.734 13.706z"
					fill="#fff"
				/><g
					fill="#c7b299"
					stroke="#000"
					stroke-linejoin="round"
					stroke-miterlimit="10"
					stroke-width="7.5046"
					><polygon points="523.06 414.38 536.88 400.54 538.73 409.66 524.89 423.51" /><polygon
						points="534.45 425.04 548.27 411.21 539.15 409.36 525.32 423.19"
					/></g
				><path
					d="m499.86 450.82c-0.707 0.726-1.863 0.726-2.585 0-0.724-0.719-0.724-1.874 0-2.588l47.344-47.355c0.724-0.71 1.893-0.71 2.601 0 0.722 0.711 0.722 1.878 0 2.602z"
					stroke-width="2.5016"
				/></g
			><line
				x1="820.46"
				x2="835.93"
				y1="583.22"
				y2="583.22"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/><path
				d="m786.05 546.22c20.435 0.738 36.4 17.901 35.663 38.336-0.736 20.435-17.902 36.401-38.338 35.662-20.431-0.738-36.401-17.9-35.659-38.334 0.736-20.439 17.901-36.402 38.334-35.664z"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/><g stroke-width="2.5016"
				><g stroke-width="2.5016"
					><path
						d="m784.24 611.61c15.678 0.255 28.601-12.243 28.856-27.919 0.257-15.674-12.247-28.594-27.925-28.848-15.678-0.259-28.591 12.242-28.845 27.919-0.254 15.676 12.24 28.593 27.914 28.848z"
						fill="#fff"
						stroke-width="2.5016"
					/></g
				><path
					d="m811.27 586.47c0.291-1.638 0.437-3.302 0.437-4.967"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/><path
					d="m774.05 607.87c15.1 5.498 32.202-3.251 36.587-18.688"
					fill="none"
					stroke="#000"
					stroke-miterlimit="10"
					stroke-width="7.5046"
				/></g
			><path
				d="m902.23 569.08h-55.653c-6.188 0-11.201 5.014-11.201 11.199v5.897c0 6.185 5.013 11.197 11.201 11.197h55.653z"
				fill="#f69823"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
				><line x1="857.32" x2="893.96" y1="576.06" y2="576.06" /><path
					d="m845.53 576.06h5.414"
				/></g
			><rect
				x="906.84"
				y="569.45"
				width="8.846"
				height="27.537"
				fill="none"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="7.5046"
			/><rect
				x="337.13"
				y="501.06"
				width="104.92"
				height="65.891"
				fill="#f69823"
				stroke-width="2.5016"
			/><path
				d="m439.95 503.16v61.693h-100.72v-61.693h100.72m4.197-4.197h-109.12v70.087h109.12v-65.89z"
				stroke-width="2.5016"
			/><path
				d="m413.48 552.31c16.802 0 21.602 4.8 21.602 4.8v-60.013s-4.8-4.798-21.602-4.798c-16.805 0-24.01 9.601-24.01 9.601v60.013s7.205-9.603 24.01-9.603z"
				fill="#fff"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="6.2539"
			/><path
				d="m389.71 561.91v-60.013s-7.206-9.601-24.007-9.601c-16.804 0-21.603 4.798-21.603 4.798v60.013s4.8-4.8 21.603-4.8c16.801 0 24.007 9.603 24.007 9.603z"
				fill="#fff"
				stroke="#000"
				stroke-miterlimit="10"
				stroke-width="6.2539"
			/><clipPath><use xlink:href="#SVGID_1_" /></clipPath><g
				clip-path="url(#SVGID_00000045615448653943012690000000638754117711156656_)"
				stroke-width="2.5016"
				><g stroke-width="2.5016"
					><path
						d="m688.7 881.9v-155.55c0.451 0.014 0.894 0.044 1.345 0.044 23.849 0 43.752-16.767 48.641-39.149h1.175l1.259-0.921c12.165-8.864 19.445-23.137 19.445-38.163 0-26.019-21.177-47.193-47.213-47.193-0.498 0-1.002 6e-3 -1.505 0.031-0.916-25.237-21.739-45.461-47.152-45.461-6.153 0-12.291 1.225-17.98 3.562-11.333-15.511-29.171-24.661-48.561-24.661-21.97 0-41.94 11.897-52.51 30.77-5.96-4.179-13.042-6.425-20.47-6.425-19.757 0-35.818 16.064-35.818 35.809 0 1.055 0.047 2.098 0.157 3.159-25.309 0.823-45.377 21.663-45.64 47.176-0.314 30.368 15.799 42.861 56.954 42.058 50.809 0 101.37 0.26 101.37 0.26 8.724 11.3 22.358 18.608 37.735 18.608 0.608 0 1.197-0.067 1.8-0.093v176.14"
						fill="#f69823"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
						><path
							d="m569.66 587.46s-13.941 2.215-20.472 9.396c-6.458 7.121-5.511 19.208-5.511 19.208"
						/><path
							d="m553.16 593.22s-5.883-10.283-7.369-19.048c-1.55-9.136 5.259-17.109 5.259-17.109"
						/><path
							d="m519.75 597.05s-10.553 2.367-15.196 8.173c-4.592 5.757-3.288 14.952-3.288 14.952"
						/><path
							d="m500.72 612.73s-11.28-10.673-10.852-19.552c0.421-8.752 3.913-15.882 3.913-15.882"
						/></g
					><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
						><path
							d="m561.36 648.38s-5.917-16.065-26.362-8.162c-13.201 5.097-11.685 19.147-11.685 19.147"
						/><path
							d="m619.73 648.21s-20.71-0.091-20.406 26.42c0.194 17.117 14.681 23.44 14.681 23.44"
						/><path
							d="m743.88 612.26s-18.646-19.514-48.068-5.136c-22.383 10.938-15.17 36.461-15.17 36.461"
						/></g
					><path
						d="m659.62 555.87s-4.698-0.377-18.879 6.761c-20.475 10.303-27.271 37.526-27.271 37.526"
						fill="none"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/><path
						d="m595.28 606.6s11.79-8.703 20.618-7.632c8.694 1.06 17.562 10.236 17.562 10.236"
						fill="none"
						stroke="#000"
						stroke-miterlimit="10"
						stroke-width="7.5046"
					/><g fill="#fff" stroke-width="2.5016"
						><path
							d="m572.9 567.04c-1.028-1.004-1.104-2.634-0.155-3.729 6.943-8.008 15.308-12.513 24.175-13.017 8.903-0.51 17.718 2.969 25.479 10.096 1.104 1.03 1.171 2.726 0.16 3.833-1.019 1.107-2.739 1.193-3.843 0.171-6.665-6.096-14.077-9.093-21.486-8.66-7.369 0.419-14.416 4.277-20.372 11.136-0.979 1.146-2.702 1.266-3.836 0.276-0.047-0.034-0.08-0.063-0.122-0.106z"
						/><path
							d="m724.68 618.81c0.982-1.053 2.609-1.164 3.724-0.238 8.162 6.764 12.851 15.029 13.553 23.881 0.707 8.891-2.572 17.779-9.527 25.696-1.002 1.128-2.699 1.234-3.829 0.249-1.129-0.998-1.254-2.714-0.255-3.84 5.944-6.802 8.773-14.277 8.178-21.675-0.583-7.355-4.598-14.315-11.587-20.119-1.167-0.957-1.325-2.673-0.362-3.828 0.036-0.046 0.064-0.084 0.105-0.126z"
						/></g
					><path
						d="m483.64 663c-0.727 0.773-1.925 0.857-2.748 0.175-6.02-4.989-9.479-11.087-9.999-17.616-0.519-6.556 1.899-13.117 7.03-18.957 0.74-0.831 1.99-0.907 2.824-0.182 0.833 0.737 0.923 2.001 0.188 2.831-4.385 5.016-6.473 10.533-6.035 15.99 0.431 5.43 3.395 10.558 8.552 14.84 0.859 0.708 0.976 1.974 0.264 2.825-0.024 0.036-0.047 0.061-0.076 0.094z"
						fill="#fff"
						stroke-width="2.5016"
					/><g fill="none" stroke="#000" stroke-miterlimit="10" stroke-width="7.5046"
						><path d="m643.31 575.01c17.319-16.419 46.865-8.765 53.933 14.083" /><path
							d="m636.22 584.77c0.875-1.843 1.924-3.605 3.133-5.252"
						/><path d="m463.44 666.58c-16.42-17.319-8.765-46.866 14.086-53.933" /><path
							d="m473.21 673.67c-1.842-0.874-3.605-1.924-5.252-3.131"
						/></g
					></g
				></g
			></g
		></g
	><g opacity={arrowToInvestor.opacity}
		><g transform="matrix(.40594 .41971 -.34764 .31493 49.072 46.222)" stroke-linecap="round"
			><g transform="matrix(.6666 0 0 1 228.23 103.69)" stroke-width="2.3409"
				><path
					d="m-1.98 3.9c61.73-8.13 119.49-1.72 194.54-3.96m-193.85 1.11c67.5-3.4 135.12 0.09 191.19 0.21"
					fill="none"
					stroke="#f08c00"
					stroke-width="4.6819"
				/></g
			><g transform="translate(164.03 103.69)" fill="none" stroke="#f08c00" stroke-width="3.8226"
				><path
					d="m165.3 11.43c9.01-6.39 16.03-5.84 26.39-10.59m-26.05 9.17c8.52-4.25 17.03-5.58 24.72-8.51"
				/><path
					d="m165.54-5.67c8.91-1.12 15.86 4.71 26.15 6.51m-25.81-7.93c8.32 1.86 16.75 6.63 24.48 8.59"
				/></g
			></g
		><g transform="translate(41.163 196.45)" fill="#fff"
			><text
				x="-23.742607"
				y="15.879724"
				dominant-baseline="alphabetic"
				fill="#ffffff"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				font-size="20px"
				style="white-space:pre"
				><tspan x="-23.742607" y="15.879724"
					><tspan fill="#ffffff" font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
						>Tell them to</tspan
					></tspan
				><tspan x="-23.742607" y="40.879723"
					><tspan fill="#ffffff" font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
						>stop polluting</tspan
					></tspan
				></text
			></g
		></g
	><g transform="matrix(1.0354 0 0 1.0354 144.56 -101.2)" opacity={impact.opacity}
		><path
			transform="translate(44.942 6.4067)"
			d="m93.288 107.28 10.37 9.6007-13.822-2.9428 8.2981 11.439-12.983-5.5829 5.907 12.838-11.644-8.0084 3.2888 13.744-9.8579-10.126 0.54425 14.122-7.693-11.855-2.2212 13.957-5.2324-13.128-4.9013 13.255-2.5708-13.896-7.3931 12.044 0.18969-14.131-9.6007 10.37 2.9428-13.822-11.439 8.2981 5.5829-12.983-12.838 5.907 8.0084-11.644-13.744 3.2888 10.126-9.8579-14.122 0.54425 11.855-7.693-13.957-2.2212 13.128-5.2324-13.255-4.9013 13.896-2.5708-12.044-7.3931 14.131 0.18969-10.37-9.6007 13.822 2.9428-8.2981-11.439 12.983 5.5829-5.907-12.838 11.644 8.0084-3.2888-13.744 9.8579 10.126-0.54425-14.122 7.693 11.855 2.2212-13.957 5.2324 13.128 4.9013-13.255 2.5708 13.896 7.3931-12.044-0.18969 14.131 9.6007-10.37-2.9428 13.822 11.439-8.2981-5.5829 12.983 12.838-5.907-8.0084 11.644 13.744-3.2888-10.126 9.8579 14.122-0.54425-11.855 7.693 13.957 2.2212-13.128 5.2324 13.255 4.9013-13.896 2.5708 12.044 7.3931z"
			fill="#fce94f"
			stop-color="#000000"
			stroke-miterlimit="2"
			stroke-width="2.0096"
		/><text
			x="101.73655"
			y="108.82299"
			fill="#000000"
			font-family="'Futura Md Bt'"
			font-size="23.619px"
			letter-spacing="0px"
			stroke-width=".48292"
			word-spacing="0px"
			style="font-feature-settings:normal;font-variant-caps:normal;font-variant-ligatures:normal;font-variant-numeric:normal;line-height:1.25"
			xml:space="preserve"
			><tspan
				x="101.73655"
				y="108.82299"
				font-family="Impact"
				stroke-width=".48292"
				text-align="center"
				text-anchor="middle">{impact.text}</tspan
			></text
		></g
	>
	<g opacity={investor.opacity} transform="translate(0 {investor.y})">
		<g transform="translate(210.18 112.12)"
			><text
				x="-0.87890381"
				y="17.620001"
				dominant-baseline="alphabetic"
				fill="#f08c00"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				font-size="20px"
				style="white-space:pre"
				><tspan font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'">Investor</tspan
				></text
			></g
		>
		<g transform="matrix(.096044 0 0 .096044 147.26 116.24)" stroke-width="5.206">
			<g stroke-width="5.206">
				<g fill="#e5e5ff">
					<circle
						transform="matrix(.7071 -.7071 .7071 .7071 -303.82 1582)"
						cx="1757.7"
						cy="1157.7"
						r="82.496"
						opacity=".4"
					/>

					<circle
						transform="matrix(.7071 -.7071 .7071 .7071 -294.25 453.39)"
						cx="400.17"
						cy="581.89"
						r="125.85"
						opacity=".4"
					/>
					<circle cx="835.48" cy="395.29" r="65.607" opacity=".4" /></g
				><g fill="#9192ff">
					<path
						d="m741.55 427.72c-4.057 0-8.155-0.32-12.175-0.951l0.388-2.47c3.893 0.611 7.86 0.92 11.792 0.92l0.457-1e-3 0.016 2.5zm13.118-1.106-0.418-2.465c4.017-0.682 8.023-1.699 11.908-3.023l0.807 2.366c-4.012 1.368-8.149 2.418-12.297 3.122zm-37.628-2.811c-4.013-1.313-7.95-2.96-11.703-4.896l1.146-2.222c3.634 1.875 7.447 3.47 11.333 4.741zm61.568-5.343-1.172-2.208c3.619-1.92 7.102-4.145 10.351-6.612l1.512 1.991c-3.356 2.549-6.953 4.846-10.691 6.829zm-84.042-6.25c-3.398-2.512-6.615-5.316-9.56-8.336l1.79-1.746c2.851 2.923 5.965 5.639 9.256 8.071zm104.18-9.042-1.813-1.722c2.811-2.961 5.406-6.177 7.712-9.559l2.065 1.408c-2.381 3.494-5.061 6.815-7.964 9.873zm-121.84-9.062c-2.418-3.452-4.575-7.134-6.414-10.944l2.252-1.087c1.78 3.69 3.869 7.254 6.21 10.597zm136.08-11.83-2.264-1.061c1.736-3.706 3.186-7.577 4.308-11.506l2.404 0.686c-1.158 4.058-2.655 8.055-4.448 11.881zm-147.09-10.939c-1.215-4.056-2.107-8.23-2.651-12.407l2.479-0.323c0.528 4.044 1.392 8.086 2.567 12.014zm154.03-13.38-2.482-0.293c0.347-2.946 0.523-5.941 0.523-8.901 0-1.122-0.025-2.258-0.075-3.377l2.497-0.111c0.052 1.155 0.078 2.329 0.078 3.488 0 3.059-0.182 6.152-0.541 9.194zm-154.8-11.624-2.499-0.081c0.137-4.216 0.619-8.458 1.434-12.607l2.453 0.482c-0.789 4.017-1.256 8.123-1.388 12.206zm151.23-13.133c-0.835-3.985-2.004-7.951-3.475-11.786l2.334-0.895c1.519 3.959 2.726 8.053 3.588 12.168zm-146.51-10.9-2.345-0.867c1.464-3.96 3.26-7.831 5.336-11.507l2.177 1.229c-2.011 3.561-3.75 7.31-5.168 11.145zm142.81-1.469c-1.5-3.82-3.312-7.535-5.385-11.041l2.151-1.272c2.142 3.62 4.012 7.455 5.561 11.399zm-130.76-19.853-1.952-1.562c2.64-3.301 5.566-6.408 8.696-9.234l1.676 1.855c-3.031 2.738-5.864 5.746-8.42 8.941zm118.29-1.219c-2.619-3.133-5.516-6.079-8.61-8.755l1.635-1.891c3.197 2.764 6.189 5.806 8.894 9.043zm-100.12-15.187-1.354-2.102c3.539-2.28 7.301-4.296 11.181-5.99l1.001 2.291c-3.759 1.641-7.401 3.593-10.828 5.801zm81.605-0.828c-3.48-2.144-7.162-4.024-10.941-5.587l0.956-2.311c3.902 1.614 7.703 3.556 11.297 5.769zm-59.163-8.985-0.625-2.421c4.097-1.059 8.302-1.79 12.5-2.173l0.227 2.489c-4.063 0.372-8.135 1.08-12.102 2.105zm36.53-0.376c-3.982-0.941-8.068-1.565-12.144-1.854l0.177-2.494c4.21 0.299 8.429 0.943 12.543 1.915z"
					/>
					<path
						d="m1529.1 1301.4-0.043-2.5c4.142-0.072 8.323-0.241 12.429-0.503l0.158 2.494c-4.142 0.265-8.363 0.436-12.544 0.509zm-12.553-0.073c-4.164-0.12-8.382-0.34-12.534-0.653l0.188-2.492c4.114 0.31 8.293 0.527 12.419 0.647zm37.601-1.529-0.275-2.484c4.106-0.456 8.253-1.016 12.324-1.663l0.393 2.469c-4.11 0.653-8.295 1.218-12.442 1.678zm-62.629-0.364c-4.126-0.506-8.305-1.12-12.421-1.823l0.422-2.465c4.077 0.697 8.217 1.306 12.304 1.808zm87.419-3.577-0.51-2.447c4.053-0.844 8.128-1.792 12.113-2.818l0.623 2.421c-4.022 1.035-8.136 1.992-12.226 2.844zm-112.16-0.655c-4.07-0.896-8.173-1.901-12.194-2.988l0.652-2.414c3.983 1.077 8.048 2.073 12.079 2.961zm136.47-5.612-0.738-2.389c3.948-1.22 7.915-2.55 11.79-3.952l0.852 2.352c-3.913 1.415-7.918 2.758-11.904 3.989zm-160.7-0.942c-3.965-1.276-7.963-2.67-11.884-4.14l0.878-2.341c3.884 1.456 7.845 2.836 11.771 4.102zm184.27-7.586-0.961-2.309c3.791-1.577 7.607-3.271 11.341-5.037l1.068 2.26c-3.769 1.782-7.621 3.493-11.448 5.086zm-207.83-1.255c-3.837-1.652-7.683-3.418-11.43-5.247l1.096-2.246c3.712 1.812 7.521 3.561 11.322 5.196zm230.47-9.452-1.174-2.207c3.636-1.935 7.277-3.982 10.824-6.089l1.276 2.15c-3.58 2.125-7.255 4.194-10.926 6.146zm-253.07-1.575c-3.651-2.001-7.31-4.12-10.878-6.3l1.303-2.133c3.535 2.159 7.161 4.259 10.776 6.239zm274.63-11.226-1.377-2.088c3.452-2.276 6.887-4.658 10.21-7.08l1.473 2.02c-3.355 2.445-6.821 4.849-10.306 7.148zm-296.07-1.876c-3.442-2.333-6.885-4.786-10.232-7.29l1.498-2.002c3.315 2.481 6.727 4.911 10.137 7.222zm316.34-12.899-1.564-1.949c3.215-2.582 6.413-5.276 9.508-8.009l1.654 1.873c-3.124 2.759-6.353 5.479-9.598 8.085zm-336.45-2.153c-3.22-2.653-6.416-5.417-9.501-8.213l1.68-1.852c3.056 2.77 6.222 5.507 9.411 8.135zm355.26-14.458-1.74-1.795c2.962-2.874 5.896-5.857 8.722-8.867l1.822 1.711c-2.851 3.038-5.813 6.05-8.804 8.951zm-373.86-2.401c-2.96-2.946-5.883-5.994-8.688-9.061l1.844-1.688c2.779 3.037 5.675 6.058 8.607 8.977zm391.04-15.906-1.9-1.623c2.688-3.147 5.332-6.394 7.857-9.647l1.975 1.533c-2.549 3.284-5.218 6.56-7.932 9.737zm-407.98-2.609c-2.668-3.206-5.292-6.513-7.799-9.828l1.994-1.508c2.483 3.285 5.083 6.561 7.727 9.736zm423.39-17.231-2.045-1.438c2.381-3.385 4.71-6.865 6.922-10.347l2.109 1.341c-2.232 3.513-4.582 7.027-6.986 10.444zm-438.51-2.779c-2.351-3.432-4.652-6.968-6.841-10.51l2.127-1.314c2.168 3.509 4.448 7.012 6.776 10.412zm451.99-18.428-2.17-1.24c2.047-3.582 4.038-7.269 5.92-10.957l2.227 1.137c-1.9 3.722-3.911 7.444-5.977 11.06zm-465.17-2.9c-2.02-3.641-3.978-7.375-5.819-11.101l2.24-1.107c1.825 3.689 3.765 7.39 5.765 10.995zm476.59-19.496-2.279-1.029c1.708-3.779 3.343-7.641 4.86-11.475l2.324 0.92c-1.532 3.872-3.182 7.769-4.905 11.584zm-487.7-2.963c-1.667-3.814-3.264-7.715-4.744-11.591l2.336-0.893c1.466 3.84 3.047 7.703 4.699 11.481zm496.96-20.427-2.365-0.809c1.333-3.9 2.593-7.891 3.743-11.86l2.4 0.695c-1.16 4.008-2.432 8.036-3.778 11.974zm-505.9-2.994c-1.304-3.969-2.527-8.012-3.635-12.018l2.41-0.666c1.097 3.968 2.308 7.973 3.6 11.902zm512.89-21.117-2.432-0.582c0.958-4.005 1.834-8.097 2.603-12.16l2.457 0.465c-0.776 4.103-1.661 8.234-2.628 12.277zm-519.58-3.078c-0.916-4.049-1.751-8.188-2.481-12.306l2.461-0.438c0.724 4.079 1.551 8.181 2.458 12.192zm524.25-21.585-2.475-0.35c0.574-4.073 1.061-8.229 1.445-12.352l2.488 0.232c-0.387 4.163-0.878 8.358-1.458 12.47zm-528.63-3.129c-0.531-4.12-0.973-8.32-1.313-12.485l2.492-0.203c0.336 4.126 0.773 8.287 1.3 12.368zm530.96-21.862-2.498-0.115c0.191-4.108 0.288-8.291 0.288-12.433h2.5c0 4.18-0.098 8.402-0.29 12.548zm-533-3.155c-0.107-3.104-0.162-6.264-0.162-9.393 0-1.056 0.01-2.109 0.018-3.162l2.5 0.03c-0.013 1.042-0.018 2.086-0.018 3.132 0 3.101 0.054 6.231 0.16 9.307zm530.72-15.537c-0.094-4.134-0.287-8.313-0.572-12.424l2.494-0.174c0.288 4.15 0.482 8.368 0.578 12.541zm-527.93-9.417-2.496-0.145c0.242-4.172 0.585-8.381 1.021-12.512l2.486 0.262c-0.432 4.092-0.772 8.262-1.011 12.395zm526.21-15.389c-0.478-4.091-1.06-8.234-1.731-12.314l2.467-0.406c0.678 4.119 1.266 8.301 1.747 12.431zm-523.6-9.338-2.471-0.378c0.63-4.123 1.367-8.282 2.191-12.361l2.451 0.495c-0.817 4.04-1.546 8.16-2.171 12.244zm519.56-15.196c-0.86-4.028-1.831-8.098-2.886-12.096l2.418-0.638c1.064 4.037 2.044 8.146 2.913 12.211zm-514.64-9.177-2.424-0.61c1.017-4.043 2.145-8.114 3.351-12.099l2.393 0.725c-1.195 3.946-2.313 7.979-3.32 11.984zm508.3-14.864c-1.242-3.939-2.594-7.898-4.019-11.769l2.346-0.863c1.438 3.907 2.804 7.904 4.058 11.88zm-501.09-8.966-2.355-0.837c1.399-3.937 2.911-7.892 4.493-11.752l2.313 0.947c-1.568 3.825-3.065 7.742-4.451 11.642zm492.51-14.34c-1.6-3.784-3.315-7.59-5.102-11.313l2.254-1.081c1.803 3.758 3.536 7.6 5.15 11.42zm-483.06-8.717-2.266-1.057c1.759-3.771 3.638-7.562 5.583-11.267l2.213 1.162c-1.927 3.671-3.788 7.427-5.53 11.162zm472.33-13.659c-1.949-3.618-4.018-7.247-6.148-10.789l2.143-1.289c2.15 3.576 4.239 7.24 6.207 10.893zm-460.75-8.387-2.156-1.266c2.11-3.593 4.337-7.189 6.617-10.685l2.094 1.365c-2.259 3.465-4.465 7.027-6.555 10.586zm447.95-12.894c-2.286-3.427-4.688-6.849-7.138-10.171l2.012-1.484c2.474 3.354 4.897 6.808 7.206 10.268zm-434.35-7.953-2.027-1.463c2.436-3.375 4.988-6.744 7.587-10.012l1.957 1.556c-2.575 3.238-5.104 6.575-7.517 9.919zm419.6-12.046c-2.6-3.202-5.313-6.386-8.063-9.464l1.865-1.666c2.775 3.107 5.514 6.321 8.139 9.553zm-404.11-7.426-1.881-1.646c2.747-3.139 5.603-6.253 8.486-9.254l1.803 1.732c-2.858 2.973-5.687 6.058-8.408 9.168zm387.55-11.115c-2.896-2.952-5.896-5.87-8.916-8.673l1.701-1.832c3.048 2.829 6.076 5.775 9 8.754zm-370.32-6.814-1.719-1.815c3.025-2.867 6.158-5.699 9.311-8.417l1.633 1.894c-3.124 2.692-6.227 5.498-9.225 8.338zm352.09-10.107c-3.146-2.658-6.406-5.283-9.691-7.804l1.521-1.983c3.316 2.544 6.608 5.195 9.783 7.878zm-333.26-6.127-1.543-1.968c3.276-2.567 6.658-5.093 10.052-7.506l1.449 2.037c-3.362 2.391-6.713 4.893-9.958 7.437zm313.52-9.02c-3.396-2.361-6.89-4.671-10.384-6.864l1.328-2.117c3.528 2.214 7.055 4.545 10.483 6.929zm-293.27-5.375-1.352-2.104c3.504-2.25 7.105-4.446 10.705-6.527l1.252 2.164c-3.566 2.062-7.134 4.238-10.605 6.467zm272.18-7.858c-3.599-2.03-7.296-4.001-10.989-5.858l1.123-2.233c3.729 1.875 7.461 3.865 11.095 5.914zm-250.68-4.567-1.148-2.221c3.691-1.907 7.481-3.754 11.266-5.488l1.041 2.273c-3.749 1.719-7.503 3.547-11.159 5.436zm228.43-6.625c-3.778-1.681-7.648-3.294-11.502-4.795l0.906-2.33c3.891 1.515 7.798 3.144 11.611 4.841zm-205.88-3.712-0.934-2.319c3.873-1.558 7.828-3.041 11.756-4.408l0.822 2.361c-3.89 1.354-7.808 2.823-11.644 4.366zm182.65-5.327c-3.916-1.313-7.913-2.55-11.882-3.675l0.682-2.405c4.006 1.136 8.042 2.384 11.995 3.71zm-159.17-2.848-0.709-2.397c3.989-1.18 8.066-2.282 12.119-3.274l0.596 2.428c-4.016 0.982-8.055 2.074-12.006 3.243zm135.25-3.934c-4.019-0.936-8.114-1.788-12.176-2.533l0.451-2.459c4.1 0.752 8.235 1.613 12.291 2.558zm-111.1-1.98-0.479-2.454c4.09-0.798 8.254-1.509 12.374-2.113l0.363 2.474c-4.082 0.597-8.206 1.302-12.258 2.093zm86.64-2.509c-4.089-0.552-8.247-1.015-12.36-1.375l0.219-2.49c4.151 0.364 8.349 0.831 12.476 1.388zm-62.04-1.099-0.246-2.488c4.136-0.409 8.348-0.727 12.517-0.943l0.129 2.497c-4.13 0.214-8.302 0.528-12.4 0.934zm37.271-1.072c-3.632-0.148-7.316-0.223-10.95-0.223-0.502-1e-3 -0.991 1e-3 -1.484 4e-3l-0.016-2.5c0.501-2e-3 1.008-1e-3 1.501-4e-3 3.667 0 7.386 0.076 11.051 0.225z"
					/>
					<path
						d="m442.33 1009c-4.195-0.025-8.424-0.198-12.569-0.517l0.191-2.492c4.086 0.313 8.256 0.484 12.393 0.509zm12.578-0.372-0.162-2.494c4.107-0.267 8.259-0.685 12.34-1.244l0.339 2.477c-4.139 0.566-8.35 0.991-12.517 1.261zm-37.649-1.551c-4.142-0.617-8.304-1.391-12.371-2.301l0.546-2.439c4.009 0.897 8.111 1.659 12.193 2.268zm62.562-1.867-0.517-2.445c4.027-0.85 8.076-1.859 12.035-2.999l0.691 2.403c-4.016 1.156-8.124 2.179-12.209 3.041zm-87.106-3.62c-4.007-1.205-8.02-2.571-11.928-4.062l0.891-2.336c3.852 1.469 7.808 2.816 11.757 4.004zm111.28-3.338-0.863-2.347c3.857-1.418 7.714-2.998 11.465-4.694l1.03 2.278c-3.806 1.721-7.719 3.324-11.632 4.763zm-134.8-5.637c-3.786-1.767-7.559-3.696-11.214-5.733l1.218-2.184c3.603 2.009 7.321 3.91 11.053 5.651zm157.7-4.713-1.19-2.198c3.614-1.958 7.208-4.075 10.681-6.293l1.346 2.107c-3.524 2.25-7.17 4.398-10.837 6.384zm-179.68-7.542c-3.493-2.29-6.95-4.738-10.274-7.275l1.517-1.987c3.278 2.501 6.686 4.914 10.129 7.171zm200.87-5.985-1.492-2.006c3.304-2.458 6.561-5.067 9.68-7.754l1.632 1.895c-3.164 2.725-6.468 5.371-9.82 7.865zm-220.87-9.278c-3.129-2.763-6.202-5.676-9.132-8.659l1.783-1.752c2.889 2.941 5.918 5.814 9.003 8.537zm239.93-7.133-1.762-1.773c2.922-2.904 5.776-5.95 8.483-9.054l1.884 1.643c-2.745 3.148-5.641 6.239-8.605 9.184zm-257.55-10.812c-2.709-3.184-5.336-6.503-7.807-9.866l2.015-1.481c2.436 3.315 5.025 6.587 7.696 9.726zm274.09-8.146-1.996-1.505c2.481-3.292 4.874-6.714 7.111-10.171l2.099 1.358c-2.27 3.507-4.697 6.979-7.214 10.318zm-288.97-12.114c-2.226-3.533-4.352-7.191-6.319-10.873l2.205-1.178c1.938 3.629 4.035 7.235 6.229 10.718zm302.64-9.013-2.19-1.204c1.987-3.615 3.866-7.345 5.585-11.087l2.271 1.044c-1.743 3.796-3.649 7.58-5.666 11.247zm-314.48-13.155c-1.697-3.815-3.276-7.738-4.693-11.66l2.352-0.85c1.396 3.866 2.952 7.732 4.625 11.493zm325-9.722-2.341-0.877c1.445-3.858 2.767-7.816 3.929-11.765l2.398 0.706c-1.179 4.006-2.52 8.021-3.986 11.936zm-333.53-13.919c-1.132-4.023-2.131-8.137-2.97-12.228l2.449-0.502c0.826 4.032 1.811 8.086 2.927 12.052zm340.63-10.209-2.443-0.531c0.874-4.02 1.613-8.127 2.197-12.207l2.475 0.355c-0.593 4.138-1.343 8.305-2.229 12.383zm-345.68-14.428c-0.542-4.136-0.942-8.35-1.188-12.524l2.496-0.147c0.243 4.116 0.637 8.27 1.171 12.347zm349.25-10.465-2.494-0.176c0.29-4.1 0.437-8.271 0.437-12.396h2.5c0 4.183-0.149 8.413-0.443 12.572zm-348.23-14.61-2.5-0.029c0.048-4.184 0.247-8.412 0.589-12.566l2.491 0.205c-0.337 4.097-0.532 8.265-0.58 12.39zm345.98-6.289c-0.196-4.124-0.541-8.282-1.027-12.36l2.482-0.296c0.493 4.137 0.843 8.355 1.042 12.538zm-343.94-18.417-2.471-0.383c0.641-4.132 1.44-8.289 2.374-12.356l2.436 0.56c-0.92 4.009-1.707 8.107-2.339 12.179zm341-6.198c-0.779-4.043-1.715-8.109-2.783-12.086l2.414-0.648c1.084 4.035 2.034 8.161 2.824 12.262zm-335.45-17.961-2.39-0.734c1.229-4.001 2.62-8.005 4.133-11.903l2.33 0.905c-1.491 3.841-2.862 7.789-4.073 11.732zm329.02-5.979c-1.351-3.884-2.861-7.769-4.488-11.546l2.296-0.989c1.651 3.833 3.183 7.773 4.554 11.714zm-320.04-17.159-2.259-1.07c1.789-3.775 3.74-7.537 5.799-11.18l2.177 1.23c-2.03 3.592-3.954 7.299-5.717 11.02zm310.24-5.584c-1.896-3.654-3.949-7.284-6.102-10.791l2.131-1.308c2.183 3.557 4.266 7.24 6.189 10.947zm-298.03-16.014-2.083-1.383c2.311-3.48 4.779-6.922 7.335-10.232l1.979 1.528c-2.519 3.263-4.953 6.657-7.231 10.087zm285.07-5.104c-2.4-3.346-4.951-6.648-7.582-9.815l1.923-1.598c2.669 3.212 5.257 6.562 7.69 9.956zm-269.91-14.525-1.864-1.665c2.783-3.116 5.714-6.171 8.712-9.082l1.741 1.794c-2.955 2.869-5.845 5.881-8.589 8.953zm254.06-4.543c-2.852-2.973-5.847-5.88-8.902-8.642l1.677-1.854c3.099 2.801 6.137 5.75 9.029 8.766zm-236.27-12.727-1.609-1.913c3.195-2.687 6.529-5.294 9.911-7.75l1.469 2.023c-3.334 2.421-6.621 4.992-9.771 7.64zm217.87-3.901c-3.248-2.539-6.626-4.992-10.043-7.291l1.395-2.074c3.466 2.332 6.894 4.819 10.188 7.395zm-197.81-10.657-1.32-2.123c3.546-2.205 7.216-4.31 10.91-6.254l1.165 2.212c-3.641 1.917-7.26 3.991-10.755 6.165zm177.23-3.187c-3.577-2.05-7.273-3.996-10.985-5.782l1.084-2.253c3.767 1.813 7.516 3.786 11.144 5.866zm-155.31-8.354-1.003-2.29c3.822-1.673 7.753-3.229 11.687-4.623l0.835 2.357c-3.877 1.373-7.753 2.906-11.519 4.556zm132.95-2.405c-3.833-1.515-7.772-2.91-11.708-4.144l0.748-2.386c3.993 1.253 7.989 2.667 11.878 4.204zm-109.6-5.871-0.663-2.41c4.023-1.107 8.143-2.081 12.245-2.898l0.487 2.452c-4.042 0.804-8.103 1.765-12.069 2.856zm85.931-1.556c-4.006-0.946-8.1-1.757-12.166-2.413l0.397-2.468c4.125 0.665 8.278 1.488 12.342 2.447zm-61.618-3.279-0.311-2.48c4.136-0.517 8.353-0.892 12.531-1.115l0.133 2.496c-4.119 0.22-8.275 0.59-12.353 1.099zm37.145-0.667c-4.095-0.362-8.262-0.582-12.385-0.653l0.043-2.5c4.183 0.073 8.409 0.296 12.563 0.663z"
					/>
					<path
						d="m1146.5 412.44c-23.261 0-42.186-18.924-42.186-42.185s18.925-42.186 42.186-42.186 42.186 18.924 42.186 42.186c-1e-3 23.261-18.926 42.185-42.186 42.185zm0-82.496c-22.228 0-40.311 18.083-40.311 40.311 0 22.227 18.083 40.31 40.311 40.31s40.311-18.083 40.311-40.31c-1e-3 -22.228-18.084-40.311-40.311-40.311z"
					/>
				</g>

				<path
					d="m1585.4 563.88v760.18c0 15.825-12.825 28.65-28.625 28.65h-1104.7c-15.825 0-28.65-12.825-28.65-28.65v-760.18c0-15.825 12.825-28.65 28.65-28.65h1104.7c15.8 0 28.625 12.825 28.625 28.65z"
					fill="#fff"
				/>
				<path
					d="m1556.8 1354h-1104.7c-16.487 0-29.9-13.413-29.9-29.9v-760.18c0-16.487 13.413-29.9 29.9-29.9h1104.7c16.473 0 29.875 13.413 29.875 29.9v760.18c0 16.487-13.402 29.9-29.875 29.9zm-1104.7-817.48c-15.108 0-27.4 12.292-27.4 27.4v760.18c0 15.108 12.292 27.4 27.4 27.4h1104.7c15.095 0 27.375-12.292 27.375-27.4v-760.18c0-15.108-12.28-27.4-27.375-27.4z"
					fill="#9192ff"
				/>

				<path
					d="m1585.4 563.88v45.1h-1162v-45.1c0-15.825 12.825-28.65 28.65-28.65h1104.7c15.8 0 28.625 12.825 28.625 28.65z"
					fill="#fff"
				/>
				<path
					d="m1586.6 610.22h-1164.5v-46.35c0-16.487 13.413-29.9 29.9-29.9h1104.7c16.473 0 29.875 13.413 29.875 29.9zm-1162-2.5h1159.5v-43.85c0-15.108-12.28-27.4-27.375-27.4h-1104.7c-15.108 0-27.4 12.292-27.4 27.4z"
					fill="#9192ff"
				/>

				<circle cx="487.92" cy="572.1" r="13.333" fill="#3335cf" />
				<path
					d="m538.75 558.77c-7.352 0-13.334 5.981-13.334 13.333s5.981 13.334 13.334 13.334 13.334-5.981 13.334-13.334c0-7.352-5.982-13.333-13.334-13.333z"
					fill="#3335cf"
				/><g fill="#9192ff">
					<path
						d="m589.58 585.43c-7.352 0-13.333-5.981-13.333-13.333s5.981-13.333 13.333-13.333 13.333 5.981 13.333 13.333c1e-3 7.352-5.98 13.333-13.333 13.333zm0-24.166c-5.974 0-10.833 4.86-10.833 10.833s4.86 10.833 10.833 10.833 10.833-4.86 10.833-10.833c1e-3 -5.973-4.859-10.833-10.833-10.833z"
					/>
					<path
						d="m917.66 586.94h-247.81c-8.185 0-14.844-6.659-14.844-14.844s6.659-14.844 14.844-14.844h247.81c8.185 0 14.844 6.659 14.844 14.844s-6.66 14.844-14.845 14.844zm-247.81-27.188c-6.806 0-12.344 5.538-12.344 12.344s5.538 12.344 12.344 12.344h247.81c6.806 0 12.344-5.538 12.344-12.344s-5.538-12.344-12.344-12.344z"
					/>

					<path
						d="m1232.8 962.72c0 119.7-97.025 216.75-216.72 216.75s-216.75-97.05-216.75-216.75c0-112.3 85.425-204.65 194.82-215.65l7.225 71.125c-73.3 7.375-130.52 69.275-130.52 144.52 0 80.225 65.025 145.25 145.22 145.25s145.2-65.025 145.2-145.25c0-14-1.975-27.525-5.675-40.325l68.725-19.85c5.525 19.1 8.475 39.3 8.475 60.175z"
					/>
				</g><circle cx="1016.1" cy="962.72" r="175" fill="#fff" />
				<circle cx="1016.1" cy="962.72" r="175" fill="#d1d1ff" opacity=".5" />

				<ellipse cx="1016.1" cy="962.72" rx="123.95" ry="123.98" fill="#fff" />

				<path
					d="m1030.2 1023.7v18.848h-23.945v-17.998c-16.977-1.016-33.443-5.607-43.632-11.886l12.899-29.213c11.212 6.624 26.143 10.869 39.221 10.869 11.378 0 15.456-2.379 15.456-6.458 0-14.942-65.71-2.883-65.71-47.211 0-19.194 13.922-35.325 41.765-39.232v-18.51h23.945v18.171c12.553 1.189 24.788 4.418 34.466 9.853l-12.055 29.04c-11.724-5.946-22.756-8.829-33.111-8.829-11.724 0-15.456 3.395-15.456 7.467 0 14.271 65.71 2.379 65.71 46.194 0 18.346-13.244 34.311-39.553 38.895z"
					fill="#9192ff"
					stroke-width="5.206"
				/>

				<rect x="1316.1" y="386.93" width="471.51" height="288.31" fill="#fff" />
				<path
					d="m1788.9 676.49h-474.01v-290.81h474.01zm-471.51-2.5h469.01v-285.81h-469.01z"
					fill="#9192ff"
				/>

				<g fill="#d1d1ff">
					<rect x="1375.5" y="583.47" width="27.138" height="49.836" />
					<rect x="1429.7" y="560.7" width="27.138" height="72.609" />
					<rect x="1484" y="579.32" width="27.138" height="53.993" />
					<rect x="1538.3" y="541.32" width="27.138" height="91.985" />
					<rect x="1592.6" y="517.02" width="27.138" height="116.28" />
					<rect x="1646.8" y="482.32" width="27.138" height="150.99" />
					<rect x="1701.1" y="428.87" width="27.138" height="204.44" />

					<rect x="1375.5" y="453.13" width="21.566" height="24.42" />
					<rect x="1430.4" y="464.43" width="146.06" height="6.259" />
				</g>

				<path
					d="m1363.3 821.42-29.864-82.489c-33.738 12.217-57.847 44.534-57.847 82.489 0 48.442 39.27 87.711 87.711 87.711s87.712-39.27 87.712-87.711c0-14.577-3.576-28.31-9.868-40.406z"
					fill="#ebebff"
				/>
				<path
					d="m1452.9 749.76c-14.617-28.101-43.979-47.306-77.844-47.306-10.487 0-20.542 1.847-29.864 5.223l29.864 82.489z"
					fill="#9192ff"
				/>

				<rect x="1280" y="1102.5" width="207.5" height="197.5" fill="#ebebff" />
				<rect x="1312.5" y="1155" width="116.25" height="8.34" fill="#fff" />
				<rect x="1312.5" y="1180" width="116.25" height="8.34" fill="#fff" />

				<rect x="515" y="725" width="180.44" height="305" fill="#ebebff" />

				<rect x="542.5" y="769.17" width="118.33" height="108.33" fill="#fff" />

				<rect
					transform="matrix(.6753 -.7376 .7376 .6753 -411.89 711.15)"
					x="600.42"
					y="743.12"
					width="2.5"
					height="160.43"
					fill="#ebebff"
				/>

				<rect
					transform="matrix(.7375 -.6753 .6753 .7375 -398.1 622.45)"
					x="521.45"
					y="822.08"
					width="160.43"
					height="2.5"
					fill="#ebebff"
				/>

				<rect x="189.02" y="849.57" width="412.71" height="271.93" fill="#fff" />
				<path
					d="m602.92 1122.7h-415.1v-274.32h415.1zm-412.71-2.386h410.32v-269.54h-410.32z"
					fill="#9192ff"
				/>

				<polyline
					points="232.5 1055.8 259.17 1005.8 314.17 1057.5 350.83 950.83 419.17 1025.8 464.17 1007.5 545.83 900.83"
					fill="#fff"
				/>
				<polygon
					points="233.6 1056.4 231.4 1055.2 258.83 1003.8 313.61 1055.3 350.34 948.43 419.5 1024.3 463.38 1006.5 544.84 900.07 546.83 901.59 464.95 1008.5 418.83 1027.3 418.24 1026.7 351.33 953.23 314.72 1059.7 259.5 1007.9"
					fill="#9192ff"
				/>
				<g fill="#9192ff">
					<circle cx="259.38" cy="1005.6" r="6.875" />
					<circle cx="313.75" cy="1056.2" r="6.875" />
					<circle cx="351.25" cy="951.25" r="6.875" />
				</g><line x1="307.87" x2="482.87" y1="894.17" y2="894.17" fill="#fff" />
				<rect x="307.87" y="892.92" width="175" height="2.5" fill="#9192ff" />

				<path
					d="m1170.3 1506.9c-7.397-48.482 2.771-99.453 28.205-141.39 25.434-41.932 65.938-74.504 112.35-90.348-26.283 18.396-42.326 48.13-53.519 78.195s-18.537 61.62-32.35 90.575-35.588 56.008-65.784 66.841z"
					fill="#9192ff"
				/>
				<path
					d="m1163 1507.3c-1.049-56.032-11.932-111.87-32.003-164.19-7.127-18.578-15.674-37.126-29.57-51.368-13.896-14.243-34.106-23.628-53.698-20.148 24.4 18.262 37.038 48.303 44.155 77.937s9.859 60.382 19.881 89.164c10.023 28.782 29.192 56.524 57.88 66.812z"
					fill="#9192ff"
				/><g fill="#d1d1ff">
					<path
						d="m1159.2 1510.9c-13.949-37.565-29.112-76.077-57.164-104.69-28.051-28.615-72.493-44.994-109.23-28.99 29.75 6.747 57.013 23.973 75.881 47.943 13.837 17.579 23.144 38.42 37.374 55.683 14.23 17.262 35.938 31.166 57.928 27.05z"
					/>
					<path
						d="m1154.7 1508.4c-5.716-41.226-11.434-83.118-5.411-124.3s25.496-82.301 60.387-104.99c-19.313 18.938-25.76 47.625-25.769 74.674-0.01 27.049 5.467 53.85 5.93 80.895s-4.908 55.776-23.202 75.7z"
					/>
					<path
						d="m1174 1502.4c13.371-34.071 27.626-69.445 54.857-93.9 17.485-15.703 39.757-26.002 63.046-29.154-16.327 13.029-26.553 32.121-35.033 51.21s-15.799 38.972-28.076 55.871-30.726 30.803-51.595 31.695z"
					/>
				</g><polygon points="1265.1 1490.5 1241.9 1606 1091.8 1606 1068.6 1490.5" fill="#fff" />
				<path
					d="m1243 1607.3h-152.23l-23.655-118.03h199.54zm-150.18-2.5h148.14l22.653-113.03h-193.44z"
					fill="#9192ff"
				/>

				<polygon
					points="1510.8 1606 1420.7 1606 1462 1572.4 1464.1 1530.1 1510.8 1536.6"
					fill="#d1d1ff"
				/>

				<rect
					transform="matrix(.6892 -.7246 .7246 .6892 -688.18 1556.8)"
					x="1469.3"
					y="1568.7"
					width="2.499"
					height="23.738"
					fill="#1b1b43"
				/>
				<rect x="1471.2" y="1555" width="30.833" height="2.5" fill="#1b1b43" />

				<polygon
					points="1619.4 1606 1529.3 1606 1567.3 1573.5 1567.3 1533.3 1616.1 1539.8"
					fill="#d1d1ff"
				/>

				<rect
					transform="matrix(.662 -.7495 .7495 .662 -651.87 1713.7)"
					x="1573"
					y="1570.3"
					width="2.499"
					height="18.667"
					fill="#1b1b43"
				/>
				<rect x="1577.5" y="1556.2" width="30.417" height="2.5" fill="#1b1b43" />

				<path
					d="m1519.9 1137.2c1.549 138.43 13.024 274.66 34.962 408.56h75.918c-15.792-102.4-22.932-226.76-14.101-391.63l-54.824-44.9z"
					fill="#fe5b52"
				/>
				<path
					d="m1459.9 1155.6-34.352 152.78c-8.254 36.711-8.828 74.732-1.684 111.68l24.131 124.79h75.918l-22.975-163.82 54.941-249.73z"
					fill="#fe5b52"
				/>
				<path
					d="m1525 1302c-0.193-3.147-4.516-73.41-4.965-82.313l-19.839-7.215 0.854-2.35 21.448 7.799v0.876c0.01 1.539 3.271 54.996 4.998 83.048z"
					fill="#be443d"
				/>

				<path
					d="m1689.4 810.62 4.063-9.688s-14.688-30.938-10-35 12.188 7.5 12.188 7.5-2.188-37.5 5-37.813c6.062-0.264 5.625 10.625 6.25 26.875 0 0 3.75-5 10.648 0.166 3.102-5.166 9.664-1.728 11.539 1.397 2.188-2.5 11.25-1.875 10 8.75-1.585 13.475-7.813 38.438-7.813 38.438l-20 16.563z"
					fill="#ffbc96"
				/>
				<path
					d="m1528.7 940 30.411-0.241c53.343-4.759 95.009-48.092 95.009-48.092l35.205-81.042 41.875 0.625-24.579 95.245c-3.53 13.679-11.135 25.962-21.807 35.22l-87.363 75.785z"
					fill="#3335cf"
				/>
				<polygon
					points="1611.2 977.5 1528.7 940 1471.7 964.17 1445.4 1009 1459.9 1155.6 1616.7 1154.2"
					fill="#3335cf"
				/>

				<path
					d="m1348.3 1023.2c-2.563-2.275-5.779-3.658-9.194-3.942-17.331-1.444-71.516-5.626-70.991-1.425 0.625 5 41.875 23.75 41.875 23.75 8.821 9.927 17.643 19.855 26.464 29.783l24.239-37.166z"
					fill="#ffbc96"
				/>
				<path
					d="m1466.5 954.1c-11.17 1.952-20.769 9.048-25.911 19.154l-46.207 90.822-33.672-29.884-24.239 37.166 8.847 9.957c13.09 14.732 28.355 34.526 48.793 38.817 10.417 2.187 20.112-2.14 27.576-9.304 5.472-5.253 10.365-11.743 14.268-18.249l18.426-30.378 58.75-116.25z"
					fill="#3335cf"
				/>

				<rect
					transform="matrix(.9953 -.0968 .0968 .9953 -95.27 145.36)"
					x="1448.5"
					y="1008.8"
					width="2.5"
					height="90.63"
					fill="#d1d1ff"
				/>
				<polygon points="1612.2 1004.4 1597.5 1017.5 1613.1 1043.4" fill="#1b1b43" />
				<path
					d="m1712.3 781.15c-5.897 0-6.354-7.728-6.357-18.646h1.875c0 12.852 1.051 16.771 4.482 16.771 0.685 0 1.272-0.274 1.798-0.837 1.672-1.792 2.32-5.979 2.519-9.738-0.13-2.718-0.064-5.084-0.024-6.067l1.872-0.028c0.016 0.231 0.184 2.758 0.041 5.87 0.259 5.091 1.117 10.123 2.814 10.632 0.95 0.285 1.771 0.163 2.515-0.371 2.023-1.458 3.159-5.582 3.75-9.266 0.052-1.582 0.224-3.419 0.558-5.548l1.863 0.174c-0.01 0.211-0.082 2.348-0.475 5.039-0.136 3.898 0.309 7.675 1.884 8.338 1.167 0.492 2.132 0.488 2.947-0.01 2.146-1.311 2.925-5.729 3.045-7.321l1.869 0.141c-0.021 0.272-0.54 6.704-3.936 8.78-1.349 0.825-2.914 0.872-4.654 0.139-0.436-0.184-1.817-0.983-2.588-3.91-0.737 2.097-1.758 3.949-3.168 4.964-1.23 0.885-2.625 1.103-4.149 0.646-1.648-0.495-2.669-2.599-3.293-5.229-0.461 1.633-1.109 3.069-2.018 4.044-0.888 0.951-1.954 1.433-3.17 1.433z"
					fill="#d28572"
				/>

				<path
					d="m1515.5 975.58c-13.325 1.075-24.975-8.85-26.05-22.15l-0.275-3.375-3.8-47.15 29.375-2.35 18.85-1.525 4.05 50.5c1.075 13.325-8.85 24.975-22.15 26.05z"
					fill="#ffbc96"
				/>
				<path
					d="m1524.2 916.45c-9.15 16.125-22.25 27.725-34.975 33.6l-3.8-47.15 29.375-2.35z"
					fill="#1b1b43"
				/>
				<path
					d="m1533.8 867.08-5.825 49.175s-18.75 17.925-46.25 17.075c-10.025-0.3-15.925-9.8-19.375-21.875-1.425-5.05-2.425-10.525-3.125-16-2.3-18.1-1.25-35.875-1.25-35.875l42.5-14.15z"
					fill="#ffbc96"
				/>
				<path
					d="m1527.3 887.29c-4.425-15.775-12.375-23.711-23.125-25.417-34.167 18.542-56.351 7.5-72.5-13.125 39.583 7.708 56.875-48.542 94.792-11.042 28.125 8.542 27.607 35.417 11.67 57.292z"
					fill="#1b1b43"
				/>

				<ellipse
					transform="matrix(.1917 -.9814 .9814 .1917 364.78 2225)"
					cx="1533.3"
					cy="891.04"
					rx="13.695"
					ry="11.875"
					fill="#ffbc96"
				/><g fill="#1b1b43">
					<path
						d="m1537.7 885.95c-1.965 0.331-3.227 1.813-4.179 3.499-0.934 1.714-1.544 3.617-1.913 5.673l-0.732 0.044c-0.312-1.099-0.314-2.268-0.127-3.392 0.187-1.129 0.571-2.228 1.146-3.241 0.58-1.004 1.346-1.95 2.371-2.617 1-0.674 2.328-1.02 3.488-0.696z"
					/>

					<path
						d="m1468.1 889.27c0 2.129-1.026 3.854-2.292 3.854s-2.292-1.726-2.292-3.854 1.026-3.854 2.292-3.854 2.292 1.725 2.292 3.854z"
					/>
					<path
						d="m1487.1 887.7c0 2.307-1.112 4.176-2.483 4.176s-2.483-1.87-2.483-4.176c0-2.307 1.112-4.177 2.483-4.177s2.483 1.87 2.483 4.177z"
					/>
					<path
						d="m1473.3 892.4c0.01 0.742-0.287 1.466-0.644 2.091-0.376 0.62-0.828 1.153-1.273 1.641-0.886 0.972-1.712 1.854-1.905 2.776-0.248 0.944 0.121 1.872 0.845 2.805 0.728 0.918 1.71 1.748 2.66 2.67l-0.404 0.611c-1.222-0.517-2.43-1.162-3.475-2.174-0.519-0.507-0.985-1.132-1.289-1.892-0.295-0.769-0.362-1.648-0.153-2.451 0.205-0.811 0.629-1.518 1.112-2.065 0.481-0.555 0.995-1.012 1.491-1.426 0.975-0.849 1.906-1.576 2.31-2.697z"
					/>
					<path
						d="m1475.1 913.23c2.639-0.587 5.086-1.423 7.273-2.785 1.094-0.671 2.128-1.449 3.12-2.303 0.992-0.855 1.939-1.784 2.925-2.729l0.595 0.429c-1.226 2.507-3.198 4.71-5.67 6.198-2.464 1.491-5.406 2.201-8.2 1.922z"
					/>
					<path
						d="m1481.6 877.35c-0.536 2.822 8.327 3.73 9.924 4.01 1.314 0.23 3.185 0.379 3.462-1.612 0.343-2.471-2.343-2.732-3.863-3.061-1.455-0.316-9.016-2.003-9.523 0.663z"
					/>
					<path
						d="m1469.2 879.09c-0.046 2.727-7.095 3-8.385 3.16-1.061 0.131-2.542 0.148-2.431-1.768 0.139-2.379 2.273-2.448 3.51-2.661 1.186-0.204 7.349-1.307 7.306 1.269z"
					/>
				</g>
				<circle cx="1502.3" cy="896.09" r="9.063" fill="#fe5b52" opacity=".2" />
				<path
					d="m1466 904.22c0 2.975-1.425 5.6-3.65 7.225-1.425-5.05-2.425-10.525-3.125-16 3.9 1.025 6.775 4.575 6.775 8.775z"
					fill="#fe5b52"
					opacity=".2"
				/>

				<rect x="646.09" y="1196.2" width="173.92" height="11.707" fill="#9192ff" />

				<polygon points="820 1196.2 673.12 1196.2 728.75 1060.6 875.62 1060.6" fill="#fff" />
				<path
					d="m820.84 1197.5h-149.58l56.65-138.12h149.58zm-145.85-2.5h144.17l54.6-133.12h-144.17z"
					fill="#9192ff"
				/>

				<polygon points="851.04 1078.3 807.32 1184.9 691.89 1184.9 735.61 1078.3" fill="#ebebff" />

				<rect x="759.03" y="1211.7" width="2.5" height="394.98" fill="#1b1b43" />
				<rect x="620" y="1208" width="280.55" height="22.314" fill="#d1d1ff" />

				<rect x="391.1" y="1377.6" width="2.5" height="229.07" fill="#1b1b43" />
				<path
					d="m460.96 1388.2h-137.22c2.913-13.93 15.195-23.91 29.427-23.91h78.366c14.232 0 26.514 9.979 29.427 23.91z"
					fill="#d1d1ff"
				/>
				<path
					d="m427.97 1606h-71.24c0-8.662 7.022-15.683 15.684-15.683h39.873c8.661-1e-3 15.683 7.021 15.683 15.683z"
					fill="#d1d1ff"
				/>

				<path
					d="m498.21 1037.7c3.51 5.045 8.541 12.189 9.098 18.433 0.808 9.077-13.716 2.714-13.887 3.499-1e-3 0 4.789-21.932 4.789-21.932z"
					fill="#d28572"
				/>

				<rect x="430.11" y="1048.4" width="45.924" height="67.302" fill="#ffbc96" />
				<path d="m476.03 1060v48.049c-14.471-9.09-26.98-22.592-37.792-38.176z" fill="#1b1b43" />

				<path
					d="m501.84 1041.8c-1.43 23.249-10.375 49.548-34.787 43.06-19.175-5.096-40.28-21.242-40.28-44.535s16.121-42.175 36.008-42.175c12.429 0 28.078 6.032 35.443 17.683 4.419 6.99 4.24 15.829 3.616 25.967z"
					fill="#ffbc96"
				/>
				<path
					d="m461.2 1035.1c6.501-17.242 21.383-18.937 21.383-18.937s34.456 34.081 32.322-1.132c-1.696-27.983-29.045-25.338-29.045-25.338-13.361-17.394-34.789-10.588-42.604-0.504s-5.042 4.286-23.445 10.84-8.571 34.537-11.848 36.553c-24.453 0-19.915 24.201-19.915 24.201l57.888 18.882 13.944-38.065z"
					fill="#1b1b43"
				/>

				<path
					d="m467.24 1037.1c3.579 6.2 2.612 13.459-2.162 16.215-4.773 2.756-11.544-0.036-15.124-6.236-3.579-6.2-2.612-13.459 2.162-16.215s11.545 0.036 15.124 6.236z"
					fill="#ffbc96"
				/>
				<path
					d="m459.84 1044.5c-0.814-1.571-1.498-3.099-2.595-4.168-0.537-0.539-1.161-0.977-1.87-1.361-0.709-0.383-1.498-0.703-2.307-1.085l0.124-0.651c0.918-0.05 1.849 0.057 2.763 0.364 0.912 0.3 1.798 0.83 2.494 1.55 0.697 0.719 1.202 1.583 1.516 2.472 0.321 0.889 0.492 1.802 0.518 2.718z"
					fill="#1b1b43"
				/>

				<ellipse
					transform="matrix(.9989 -.0473 .0473 .9989 -45.977 21.794)"
					cx="437.23"
					cy="981.78"
					rx="19.455"
					ry="21.077"
					fill="#1b1b43"
				/>
				<circle cx="481.88" cy="1055" r="8.75" fill="#fe5b52" opacity=".2" />

				<path
					d="m516.25 1281.2-147.08-18.75 27.725-146.18c1.95-10.225 8.75-18.9 18.225-23.2 7.9-3.6 16.925-3.825 25.025-0.65l50.125 22.275c9.65 4.275 16.3 13.35 17.5 23.825l2.825 47.75 3.225 54.125z"
					fill="#ffa121"
				/>
				<path
					d="m650.83 1176.2 38.929-11.443c2.805-0.825 5.819-0.372 8.255 1.245 10.655 7.073 39.019 27.088 31.858 35.271-3.575 4.086-36.126-5.49-36.126-5.49l-47.131 13.151z"
					fill="#ffbc96"
				/>
				<path d="m513.82 1240.4c-12.25-15.6-19.525-36.2-21.95-61.7l18.725 7.575z" fill="#1b1b43" />
				<path
					d="m485.83 1112.9 5.86 2.526c12.064 5.2 22.876 12.923 31.707 22.649l48.266 53.158 79.167-15 10.417 42.5-99.473 31.088c-7.855 1.399-15.88-1.311-21.278-7.185l-71.749-78.069z"
					fill="#ffa121"
				/>
				<path
					d="m570.75 1192.1c-0.235-0.256-23.784-25.896-44.179-48.764-20.162-22.606-50.901-33.597-51.209-33.705l0.829-2.359c0.314 0.11 31.645 11.302 52.246 34.4 20.383 22.854 43.919 48.48 44.154 48.736z"
					fill="#1b1b43"
				/>

				<rect
					transform="matrix(.7182 -.6958 .6958 .7182 -697.77 693.28)"
					x="505.87"
					y="1160.2"
					width="2.501"
					height="95.932"
					fill="#1b1b43"
				/>

				<polygon
					points="538.02 1556.5 555.42 1517.9 510.92 1502.3 479.19 1564.1 559.34 1605.3"
					fill="#d1d1ff"
				/>

				<rect
					transform="matrix(.9593 -.2824 .2824 .9593 -419.05 212.19)"
					x="514.76"
					y="1558.6"
					width="23.739"
					height="2.5"
					fill="#1b1b43"
				/>

				<path
					d="m560.83 1543-72.61-27.092 49.723-154.72c8.548-22.91 34.878-34.243 58.809-25.314 23.932 8.929 36.403 34.74 27.855 57.649z"
					fill="#26289c"
				/>

				<polygon
					points="687.18 1572.4 677.5 1530 631.25 1532.5 638.34 1606 728.43 1606"
					fill="#d1d1ff"
				/>

				<rect
					transform="matrix(.8757 -.4828 .4828 .8757 -677.91 522.73)"
					x="664.32"
					y="1577"
					width="24.385"
					height="2.5"
					fill="#1b1b43"
				/>

				<path
					d="m696.25 1541.2-78.75 12.5-53.925-158.58-9.825-28.925-133.92 1.075c-33.125 0.75-59.475-27.625-56.225-60.625l5.575-44.2 132.5 16.675 87.075 9.575c36.25 6.25 47.375 28.2 54.925 56.4z"
					fill="#3335cf"
				/>
				<path
					d="m563.58 1395.2-9.825-28.925 18.125-0.625c1.675 10.9-2.65 23.075-8.3 29.55z"
					fill="#1b1b43"
				/>

				<rect x="241.25" y="1604.8" width="1517.5" height="2.5" fill="#1b1b43" />
			</g>
		</g></g
	><g opacity={arrowToPolluter.opacity}
		><g transform="matrix(.40594 -.41971 -.34764 -.31493 274.47 346.5)" stroke-linecap="round"
			><g transform="matrix(.6666 0 0 1 228.23 103.69)" stroke-width="2.3409"
				><path
					d="m-1.98 3.9c61.73-8.13 119.49-1.72 194.54-3.96m-193.85 1.11c67.5-3.4 135.12 0.09 191.19 0.21"
					fill="none"
					stroke="#f08c00"
					stroke-width="4.6819"
				/></g
			><g transform="translate(164.03 103.69)" fill="none" stroke="#f08c00" stroke-width="3.8226"
				><path
					d="m165.3 11.43c9.01-6.39 16.03-5.84 26.39-10.59m-26.05 9.17c8.52-4.25 17.03-5.58 24.72-8.51"
				/><path
					d="m165.54-5.67c8.91-1.12 15.86 4.71 26.15 6.51m-25.81-7.93c8.32 1.86 16.75 6.63 24.48 8.59"
				/></g
			></g
		><g transform="translate(349.7 205.41)" fill="#fff"
			><text
				x="18.398273"
				y="-10.619597"
				dominant-baseline="alphabetic"
				fill="#ffffff"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				font-size="20px"
				font-weight={arrowToPolluter.bold == 1 ? 'bold' : 'normal'}
				style="white-space:pre"
				><tspan x="18.398273" y="-10.619597">Please</tspan><tspan x="18.398273" y="14.380402"
					>stop</tspan
				></text
			></g
		></g
	><g opacity={noThanks.opacity}
		><g
			transform="matrix(.34273 0 0 .34056 350.18 -24.425)"
			stroke="#fff"
			stroke-linecap="round"
			stroke-width="8.5676"
			><g transform="translate(347.11 110.74)"
				><path
					d="m44.182 112.9c0.35366 0.15077 0.69048 0.31786 1.0479 0.46484 10.382 4.265 23.654 7.4226 36.691 9.7441 8.0932 1.9979 16.479 3.6662 24.879 4.6455 15.62 1.82 32.89 1.9798 48.8 0.58985 14.813-1.295 30.419-4.3605 43.72-8.0957 10.547-2.0373 20.553-4.4664 28.881-8.0537 11.71-5.05 21.88-12.61 28.35-19.88 1.6296-1.8314 3.0259-3.748 4.2256-5.7148 1.0254-1.181 1.9825-2.3638 2.7744-3.5459 4.85-7.23 5.8504-15.18 4.4404-22.77-0.12521-0.67881-0.30542-1.3652-0.48047-2.0508-0.29976-4.4632-1.4321-8.8969-4.1201-13.18-4.77-7.59-14.98-15.79-25.01-22.02-10.04-6.23-21.39-11.67-35.21-15.34-11.191-2.9739-25.18-5.5865-38.49-6.3926-5.5606-0.82874-11.19-1.4793-16.694-1.7656-0.27729-0.026572-0.65613-0.042254-1.0635-0.053711-1.931-0.084441-3.8446-0.12768-5.7295-0.11426-0.99558 0.00709-1.9841 0.028906-2.9629 0.066406l1.1504 0.23633c-11.469 0.44802-35.297 1.5558-50.11 3.9834-16.12 2.63-30.92 6.3899-43.29 11.67-12.37 5.27-23.35 13.11-30.93 19.99-0.35927 0.32605-0.68446 0.6524-1.0322 0.97852-4.7427 3.9233-8.6893 8.0343-11.178 12.182-4.32 7.19-5.2304 15.139-3.1904 22.699 0.58018 2.1472 1.4928 4.3352 2.6338 6.5283 0.3878 0.9115 0.81296 1.8116 1.2861 2.6924 3.8639 7.2018 10.881 14.471 19.987 20.49 0.79843 0.6019 1.6165 1.1956 2.4512 1.7881"
					fill="none"
					stroke="#fff"
					stroke-width="2.9271"
				/></g
			><g transform="translate(337.11 100.74)"
				><g transform="translate(36 110.82)" stroke="#fff" stroke-width="2.9271"
					><path
						d="m-1.15 1.16c-3.06 6.94-20.74 38.23-17.15 39.87 3.58 1.65 32.32-24.95 38.68-30m-19.93-10.31c-2.67 6.69-19.65 36.93-16.41 38.81 3.24 1.87 29.85-22.85 35.87-27.55"
						fill="none"
						stroke="#fff"
						stroke-width="2.9271"
					/></g
				></g
			></g
		><text
			x="477.26086"
			y="41.405224"
			fill="#fcfcfc"
			font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
			font-size="16.298px"
			letter-spacing="0px"
			stroke-width=".5"
			word-spacing="0px"
			style="font-feature-settings:normal;font-variant-caps:normal;font-variant-ligatures:normal;font-variant-numeric:normal;line-height:1.25"
			xml:space="preserve"
			><tspan
				x="477.26086"
				y="41.405224"
				fill="#fcfcfc"
				font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
				stroke-width=".5">No thanks</tspan
			></text
		></g
	><g
     id="g37137"
	 opacity={cannotMeasure.opacity}
	 ><g
       id="g36666"
       style="fill:none;fill-opacity:1;stroke:#f08c00;stroke-width:1.95;stroke-dasharray:none;stroke-opacity:1"
       transform="translate(-2.330187,-25.356097)"><path
         style="fill:none;fill-opacity:1;stroke:#f08c00;stroke-width:1.95;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:none;stroke-opacity:1"
         d="m 416.05513,230.53056 c 8.82739,6.68438 25.60716,30.5913 36.19354,30.5913"
         id="path36660" /><path
         style="fill:none;fill-opacity:1;stroke:#f08c00;stroke-width:1.95;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:none;stroke-opacity:1"
         d="m 417.16864,247.47654 c 0.29917,-5.16671 1.11961,-9.39098 1.11961,-14.52567 0,-0.61995 -1.30236,-1.20915 -0.86364,-1.64717 0.0943,-0.0942 12.31841,2.59557 14.02279,2.59557"
         id="path36662" /></g><text
       x="449.75528"
       y="217.50305"
       font-family="Excalifont, Xiaolai, sans-serif, 'Segoe UI Emoji'"
       font-size="11.2392px"
       fill="#f08c00"
       text-anchor="start"
       style="white-space:pre;fill:#ffffff;stroke-width:1"
       direction="ltr"
       dominant-baseline="alphabetic"
       id="text5387-6-0-3"><tspan
         sodipodi:role="line"
         x="449.75528"
         y="217.50305"
         id="tspan23186-5"
         style="fill:#f08c00;fill-opacity:1;stroke-width:1">We</tspan><tspan
         sodipodi:role="line"
         x="449.75528"
         y="231.55205"
         id="tspan37123"
         style="fill:#f08c00;fill-opacity:1;stroke-width:1">cannot</tspan><tspan
         sodipodi:role="line"
         x="449.75528"
         y="245.60104"
         id="tspan37125"
         style="fill:#f08c00;fill-opacity:1;stroke-width:1">measure</tspan><tspan
         sodipodi:role="line"
         x="449.75528"
         y="259.65005"
         id="tspan37127"
         style="fill:#f08c00;fill-opacity:1;stroke-width:1">this</tspan></text></g></svg
>
