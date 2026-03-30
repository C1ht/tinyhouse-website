<!-- Accordion.svelte -->
<script>
	import { slide } from 'svelte/transition';
	let { items = [], variant = 'default', multiple = false } = $props();

	let openItems = $state([]);

	function toggle(index) {
		if (multiple) {
			openItems = openItems.includes(index)
				? openItems.filter((i) => i !== index)
				: [...openItems, index];
		} else {
			openItems = openItems.includes(index) ? [] : [index];
		}
	}

	function isOpen(index) {
		return openItems.includes(index);
	}

	const variants = {
		default: {
			wrapper: 'divide-y divide-accordion-border border border-accordion-border rounded-accordion',
			trigger: 'hover:bg-accordion-hover text-accordion-text',
			content: 'text-accordion-content-text'
		},
		ghost: {
			wrapper: 'divide-y divide-accordion-border',
			trigger: 'hover:bg-ghost-hover text-accordion-text',
			content: 'text-accordion-content-text'
		},
		filled: {
			wrapper: 'space-y-2',
			trigger:
				'bg-accordion-filled hover:bg-accordion-filled-hover text-accordion-text rounded-accordion',
			content: 'text-accordion-content-text'
		}
	};

	const v = variants[variant];
</script>

<div class={v.wrapper}>
	{#each items as item, i}
		<div class="overflow-hidden">
			<button
				onclick={() => toggle(i)}
				aria-expanded={isOpen(i)}
				style="padding-inline: var(--px-accordion); padding-block: var(--py-accordion); transition: var(--transition);"
				class="flex w-full items-center justify-between text-left font-medium {v.trigger}"
			>
				<span>{item.title}</span>
				<svg
					style="transition: var(--transition); transform: {isOpen(i)
						? 'rotate(180deg)'
						: 'rotate(0deg)'};"
					xmlns="http://www.w3.org/2000/svg"
					width="16"
					height="16"
					viewBox="0 0 24 24"
					fill="none"
					stroke="currentColor"
					stroke-width="2"
					stroke-linecap="round"
					stroke-linejoin="round"
				>
					<path d="m6 9 6 6 6-6" />
				</svg>
			</button>

			{#if isOpen(i)}
				<div
					transition:slide={{ duration: 150 }}
					style="padding-inline: var(--px-accordion); padding-bottom: var(--py-accordion);"
					class="text-sm {v.content}"
				>
					{item.content}
				</div>
			{/if}
		</div>
	{/each}
</div>
