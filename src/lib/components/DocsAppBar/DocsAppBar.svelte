<script lang="ts">

    // Types
    import type { ModalSettings, DrawerSettings } from '@skeletonlabs/skeleton';

    // Docs
    import DocsIcon from '$lib/components/DocsIcon/DocsIcon.svelte';

    // Components & Utilities
    import { LightSwitch, popup, getModalStore } from '@skeletonlabs/skeleton';

    import Icon from '@iconify/svelte';


    // Local
    let isOsMac = false;
    const modalStore = getModalStore();



    // Search
    function triggerSearch(): void {
        const modal: ModalSettings = {
            type: 'component',
            component: 'modalSearch',
            position: 'item-start'
        };
        modalStore.trigger(modal);
    }

</script>


<!-- :DocsAppBar -->
<div class="bg-orange-400 py-4 px-3">
    <div class="bg-green-400 flex">
        <!-- Explore -->
        <div class="relative hidden lg:block">
            <!-- trigger -->
            <button class="btn hover:variant-soft-primary" use:popup={{ event: 'click', target: 'features' }}>
                <span>Explore</span>
                <Icon icon="fa-brands:discord" />
            </button>
            <!-- popup -->
            <div class="card p-4 w-60 shadow-xl" data-popup="features">
                <nav class="list-nav">
                    <ul>
                        <li>
                            <a href="/">
                                <span class="w-6 text-center"><i class="fa-solid fa-home"></i></span>
                                <span>Homepage</span>
                            </a>
                        </li>
                        <li>
                            <a href="/docs/get-started">
                                <span class="w-6 text-center"><i class="fa-solid fa-book"></i></span>
                                <span>Documentation</span>
                            </a>
                        </li>
                        <li>
                            <a href="/blog">
                                <span class="w-6 text-center"><i class="fa-solid fa-bullhorn"></i></span>
                                <span>Blog</span>
                            </a>
                        </li>
                        <!-- <li>
    <a href="https://store.skeleton.dev" target="_blank">
    <span class="w-6 text-center"><i class="fa-solid fa-shopping-cart" /></span>
    <span>Skeleton Store</span>
    </a>
    </li> -->
                        <hr class="!my-4" />
                        <li>
                            <a href="/elements/core">
                                <span class="w-6 text-center"><DocsIcon name="mdi:apple" width="w-5" height="h-5" /></span>
                                <span>Tailwind</span>
                            </a>
                        </li>
                        <li>
                            <a href="/actions/clipboard">
                                <span class="w-6 text-center"><DocsIcon name="mdi:apple" width="w-5" height="h-5" /></span>

                                <span>Svelte</span>
                            </a>
                        </li>
                        <li>
                            <a href="/utilities/codeblocks">
                                <span class="w-6 text-center"><DocsIcon name="mdi:wrench" width="w-5" height="h-5" /></span>
                                <span>Utilities</span>
                            </a>
                        </li>
                    </ul>
                </nav>
                <!-- <div class="arrow bg-surface-100-800-token" /> -->
            </div>
        </div>

        <!-- Theme -->
        <div>
            <!-- trigger -->
            <button class="btn hover:variant-soft-primary"
                    use:popup={{ event: 'click', target: 'theme', closeQuery: 'a[href]' }}>
                <Icon icon="mdi:palette-swatch-variant opacity-50 text-lg md:!hidden" />
                <span class="hidden md:inline-block">Theme</span>
                <Icon icon="mdi:caret-down opacity-50" />
            </button>
            <!-- popup -->
            <div class="card p-4 w-60 shadow-xl" data-popup="theme">
                <div class="space-y-4">
                    <section class="flex justify-between items-center">
                        <h6 class="h6">Mode</h6>
                        <LightSwitch />
                    </section>
                    <hr />
                    <nav class="list-nav p-4 -m-4 max-h-64 lg:max-h-[500px] overflow-y-auto">
                        <form method="POST">
                            <ul>
                                <!-- , badge -->

                                <li>
                                    ::button::
                                </li>

                            </ul>
                        </form>
                    </nav>
                    <hr />
                    <div>
                        <a class="btn variant-filled w-full" href="/docs/generator">
                            <i class="fa-solid fa-palette"></i>
                            <span>Create a Theme</span>
                        </a>
                    </div>
                </div>
                <!-- <div class="arrow bg-surface-100-800-token" /> -->
            </div>
        </div>

        <!-- Sponsor -->
        <div>
            <!-- trigger -->
            <button class="btn hover:variant-soft-primary" use:popup={{ event: 'click', target: 'sponsor' }}>
                <i class="fa-solid fa-heart text-lg md:!hidden"></i>
                <span class="hidden md:inline-block">Sponsor</span>
                <i class="fa-solid fa-caret-down opacity-50"></i>
            </button>
            <!-- popup -->
            <div class="card p-4 w-60 shadow-xl" data-popup="sponsor">
                <div class="space-y-4">
                    <nav class="list-nav">
                        <ul>
                            <li>
                                <a href="https://github.com/sponsors/skeletonlabs" target="_blank" rel="noreferrer">
                                    <span class="w-6 text-center"><i class="fa-brands fa-github"></i></span>
                                    <span>GitHub</span>
                                </a>
                            </li>
                            <li>
                                <a href="https://ko-fi.com/skeletonlabs" target="_blank" rel="noreferrer">
                                    <span class="w-6 text-center"><i class="fa-solid fa-mug-saucer"></i></span>
                                    <span>Ko-Fi</span>
                                </a>
                            </li>
                            <li>
                                <a href="https://patreon.com/user?u=83786276" target="_blank" rel="noreferrer">
                                    <span class="w-6 text-center"><i class="fa-brands fa-patreon"></i></span>
                                    <span>Patreon</span>
                                </a>
                            </li>
                        </ul>
                    </nav>
                    <hr />
                    <div>
                        <a class="btn variant-filled w-full" href="/docs/sponsorship">
                            <i class="fa-solid fa-gift"></i>
                            <span>Incentives</span>
                            <span class="badge variant-filled-secondary">New</span>
                        </a>
                    </div>
                </div>
                <!-- <div class="arrow bg-surface-100-800-token" /> -->
            </div>

        </div>

        <!-- Version -->
        <div class="relative hidden lg:block">
            <!-- trigger -->
            <button class="btn hover:variant-soft-primary" use:popup={{ event: 'click', target: 'version' }}>
                <span>Version</span>
                <i class="fa-solid fa-caret-down opacity-50"></i>
            </button>
            <!-- popup -->
            <div class="card p-4 w-60 shadow-xl" data-popup="version">
                <nav class="list-nav">
                    <ul>
                        <li>
                            <a href="https://v1.skeleton.dev/" target="_blank">
                                <span>Skeleton v1 Docs</span>
                                <span class="w-6 text-center"><i
                                    class="fa-solid fa-arrow-up-right-from-square opacity-50"></i></span>
                            </a>
                        </li>
                    </ul>
                </nav>
                <!-- <div class="arrow bg-surface-100-800-token"></div> -->
            </div>
        </div>

        <!-- Search -->
        <div class="md:inline md:ml-4">
            <button class="btn space-x-4 variant-soft hover:variant-soft-primary" on:click={triggerSearch}>
                <i class="fa-solid fa-magnifying-glass text-sm"></i>
                <small class="hidden md:inline-block">{isOsMac ? '⌘' : 'Ctrl'}+K</small>
            </button>
        </div>

        <!-- Social -->
        <section class="hidden sm:inline-flex space-x-1">
            <a class="btn-icon hover:variant-soft-primary" href="https://github.com/skeletonlabs/skeleton" target="_blank"
            rel="noreferrer">
                <Icon icon="fa-brands:discord" />
            </a>
            <a class="btn-icon hover:variant-soft-primary" href="https://discord.gg/EXqV7W8MtY" target="_blank"
            rel="noreferrer">
                <Icon icon="fa-brands:discord" />
            </a>
        </section>
    </div>

</div>

