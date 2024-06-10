

<script lang="ts">
    import Icon from '@iconify/svelte';

    // Props
	/** Pass canned svg name. Slot value overrides this.*/
export let name = 'mdi:compass';
</script>


::DocIcon::
<Icon icon={name} />