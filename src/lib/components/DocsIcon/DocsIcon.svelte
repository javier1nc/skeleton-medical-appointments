<script lang="ts">
    import Icon from '@iconify/svelte';

    // Props
	/** Pass canned svg name. Slot value overrides this.*/
    export let name = 'mdi:compass';


    // Props (Styles)
	/** Provide classes to set the SVG fill color.*/
	export let fill = 'fill-current';
	/** Provide classes to set the width color.*/
	export let width = 'w-5';
	/** Provide classes to set the height color.*/
	export let height = 'h-5';

    // Base Classes
	const cBase = 'inline-block outline-none';

	// Reactive Classes
	$: classesBase = `${cBase} ${fill} ${width} ${height}`;
</script>


<!-- ::DocIcon:: -->
<Icon icon={name}  class={classesBase}/>