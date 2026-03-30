<script>
	let { label = 'Button', href = '#', variant= "primary" } = $props();
	const variants = {
		primary: "bg-primary hover:bg-primary-hover text-primary-text",
		danger: "bg-danger hover:bg-danger-hover text-secondary-text",
		secondary: "bg-secondary hover:bg-secondary-hover text-secondary-text",
		outline: "bg-outline hover:bg-outline-hover text-outline-text border border-outline-border",
		ghost: "bg-ghost hover:bg-ghost-hover text-ghost-text",
		link: "hover:underline text-link-text",
		logo: "font-bold",
	}
</script>

<a href={href} style="padding-inline: var(--px-btn); padding-block: var(--px-btn); border-radius: var(--radius-btn); transition: var(--transition);" class={variants[variant]}>{label}</a>