<script>
  import Button from '$lib/components/ui/buttons.svelte';
  import Accordion from '$lib/components/ui/accordion.svelte';

  const items = [
    { title: 'Example', content: 'Example' },
    { title: 'Example', content: 'Example' },
    { title: 'Example', content: 'Example' },
  ];
</script>
<div class="m-auto my-16 w-fit">
<Button variant="primary"/>
<Button variant="secondary" />
<Button variant="danger" />
<Button variant="outline" />
<Button variant="ghost" />
<Button variant="link" />
</div> 
<div class="max-w-lg m-auto">
    <Accordion {items} />
</div>