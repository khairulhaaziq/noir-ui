<script lang="ts">
	import { writable, type Writable } from 'svelte/store';
	import { setContext } from 'svelte';

    export let open: Writable<boolean> = writable(false);
    export let defaultOpen = false
    export let dir: "ltr" | "rtl" = "ltr"

    let value: Writable<string | undefined> = writable(undefined);
    let highlighted: Writable<string | undefined> = writable(undefined);
    let portalElement: Writable<HTMLElement | null> = writable(null);
	let triggerButton: Writable<HTMLElement | null> = writable(null);
    let menuPosition: Writable<{x:number, y:number}> = writable({x: 0, y:0});

    setContext('selected', value)
    setContext('open', open)
    setContext('portalElement', portalElement)
    setContext('triggerButton', triggerButton)
    setContext('highlighted', highlighted)
    setContext('menuPosition', menuPosition)

</script>

<slot />