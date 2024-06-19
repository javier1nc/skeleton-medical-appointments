<script lang="ts">
    import '../app.postcss';

    // Highlight JS
    import hljs from 'highlight.js/lib/core';
    import 'highlight.js/styles/github-dark.css';
    import { storeHighlightJs } from '@skeletonlabs/skeleton';
    import xml from 'highlight.js/lib/languages/xml'; // for HTML
    import css from 'highlight.js/lib/languages/css';
    import javascript from 'highlight.js/lib/languages/javascript';
    import typescript from 'highlight.js/lib/languages/typescript';

    hljs.registerLanguage('xml', xml); // for HTML
    hljs.registerLanguage('css', css);
    hljs.registerLanguage('javascript', javascript);
    hljs.registerLanguage('typescript', typescript);
    storeHighlightJs.set(hljs);

    // Floating UI for Popups
    import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
    import { storePopup } from '@skeletonlabs/skeleton';

    storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });

	// Components & Utilities
	import { Modal, Toast, initializeStores, prefersReducedMotionStore } from '@skeletonlabs/skeleton';
	initializeStores();

    // Docs Components
    import DocsAppBar from '$lib/components/DocsAppBar/DocsAppBar.svelte';
    import DocsSidebar from '$lib/components/DocsSidebar/DocsSidebar.svelte';
    import DocsDrawer from '$lib/components/DocsDrawer/DocsDrawer.svelte';
    import DocsFooter from '$lib/components/DocsFooter/DocsFooter.svelte';

</script>

<!-- Overlays -->
<Modal />
<Toast />
<DocsDrawer />

<!-- App Layout -->
<div class="page">
    <!-- Header -->
    <div class="header header-footer">
        <DocsAppBar />
    </div>

    <!-- Main -->
    <div class="flex">
        <!-- Sidebar (Left) -->
        <div class="hidden overflow-hidden">
            <DocsSidebar class="lg:grid w-[360px] " />
        </div>

        <div class="w-full flex flex-col">
            <!-- Page Content -->
            <div class="content">
                <slot />
            </div>

            <!-- Page Footer -->
            <div class="header-footer ">
                <DocsFooter />
            </div>
        </div>

    </div>
</div>

<style>
    .page {
        @apply h-screen flex flex-col;
    }

    .header-footer {
        @apply sticky;
    }

    .header {
        @apply h-screen flex flex-col top-0 z-40;
    }

    .footer {
        @apply bottom-0;
    }

    .content {
        @apply grow;
    }
</style>

