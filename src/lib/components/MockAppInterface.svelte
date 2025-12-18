<script lang="ts">
    // Mock data for the interface
    const favorites = [
        { name: "Engineering Team", icon: "team" },
        { name: "Q4 Reviews", icon: "doc" },
        { name: "Direct Reports", icon: "user" },
        { name: "1:1 Notes", icon: "doc" }
    ];

    const channels = [
        { name: "Engineering", icon: "hash", color: "bg-blue-100 text-blue-600" },
        { name: "Product", icon: "hash", color: "bg-purple-100 text-purple-600" },
        { name: "Design", icon: "hash", color: "bg-pink-100 text-pink-600" },
        { name: "Backend", icon: "hash", color: "bg-green-100 text-green-600" },
        { name: "Frontend", icon: "hash", color: "bg-orange-100 text-orange-600" },
        { name: "Mobile", icon: "hash", color: "bg-indigo-100 text-indigo-600" },
        { name: "DevOps", icon: "hash", color: "bg-cyan-100 text-cyan-600" },
        { name: "Data", icon: "hash", color: "bg-yellow-100 text-yellow-600" }
    ];

    const posts = [
        {
            title: "Shipped authentication refactor ahead of schedule",
            author: "Sarah Chen",
            preview: "Completed 3 days early, improved test coverage to 95%",
            tag: "Achievement",
            tagColor: "text-green-600",
            icon: "✓",
            iconBg: "bg-green-100"
        },
        {
            title: "Led design review for new onboarding flow",
            author: "Marcus Rodriguez",
            preview: "Facilitated cross-team alignment, incorporated feedback from 5 stakeholders",
            tag: "Leadership",
            tagColor: "text-blue-600",
            icon: "★",
            iconBg: "bg-blue-100"
        },
        {
            title: "Mentored junior dev on API design patterns",
            author: "Alex Kim",
            preview: "1:1 session focused on REST best practices and error handling",
            tag: "Growth",
            tagColor: "text-purple-600",
            icon: "↑",
            iconBg: "bg-purple-100"
        },
        {
            title: "Resolved critical production bug in payment flow",
            author: "Jordan Lee",
            preview: "Quick response, root cause analysis completed, monitoring added",
            tag: "Impact",
            tagColor: "text-orange-600",
            icon: "⚡",
            iconBg: "bg-orange-100"
        }
    ];

    const yesterdayPosts = [
        {
            title: "Presented Q4 roadmap to executive team",
            author: "Sarah Chen",
            preview: "Received approval for 3 major initiatives, budget increased by 20%",
            tag: "Leadership",
            tagColor: "text-blue-600",
            icon: "★",
            iconBg: "bg-blue-100"
        },
        {
            title: "Collaborated with Design on mobile redesign",
            author: "Marcus Rodriguez",
            preview: "Productive brainstorming session, aligned on technical constraints",
            tag: "Collaboration",
            tagColor: "text-pink-600",
            icon: "◆",
            iconBg: "bg-pink-100"
        },
        {
            title: "Improved API response time by 40%",
            author: "Jordan Lee",
            preview: "Implemented caching strategy, reduced database queries",
            tag: "Achievement",
            tagColor: "text-green-600",
            icon: "✓",
            iconBg: "bg-green-100"
        }
    ];

    const team = [
        { name: "Sarah Chen", status: "Senior Engineer", online: true, img: "https://i.pravatar.cc/150?u=sarah", performance: "On track" },
        { name: "Marcus Rodriguez", status: "Lead Designer", online: true, img: "https://i.pravatar.cc/150?u=marcus", performance: "Exceeding" },
        { name: "Alex Kim", status: "Backend Engineer", online: true, img: "https://i.pravatar.cc/150?u=alex", performance: "On track" },
        { name: "Jordan Lee", status: "Full Stack Engineer", online: true, img: "https://i.pravatar.cc/150?u=jordan", performance: "On track" },
        { name: "Taylor Morgan", status: "Product Manager", online: true, img: "https://i.pravatar.cc/150?u=taylor", performance: "Exceeding" },
        { name: "Casey Park", status: "DevOps Engineer", online: false, img: "https://i.pravatar.cc/150?u=casey", performance: "On track" }
    ];
</script>

<div class="rounded-xl border border-gray-200 bg-white shadow-2xl overflow-hidden flex h-[800px] text-sm select-none relative z-10">
    <!-- Left Sidebar -->
    <div class="w-64 bg-gray-50 border-r border-gray-200 flex flex-col flex-shrink-0">
        <!-- Header -->
        <div class="p-3 border-b border-gray-200 flex items-center justify-between">
            <div class="flex items-center gap-2 font-medium text-gray-900">
                <svg width="20" height="20" viewBox="0 0 112 106" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M111.712 30.2285V0C92.366 0 73.5034 6.52934 59.961 17.8952L56.3336 20.7972L52.7062 17.8952C38.922 6.52934 20.3013 0 0.955078 0V30.2285C0.955078 38.4506 3.85704 46.1891 8.6936 52.7184C3.85704 59.2478 0.955078 66.9863 0.955078 75.2085V105.437C20.3013 105.437 39.1639 98.9076 52.7062 87.5417L56.3336 84.6397C46.9023 79.0777 41.0985 69.1627 41.0985 58.0387V47.3983C41.0985 36.516 46.9023 26.3592 56.3336 20.7972C65.7649 26.3592 71.5688 36.516 71.5688 47.3983V58.0387C71.5688 68.9209 65.7649 79.0777 56.3336 84.6397L59.961 87.5417C73.7452 98.9076 92.366 105.437 111.712 105.437V75.2085C111.712 66.9863 108.81 59.2478 103.974 52.7184C108.81 46.1891 111.712 38.4506 111.712 30.2285Z" fill="#201B21"/>
                </svg>
                Engineering
                <svg class="w-3 h-3 text-gray-400" viewBox="0 0 16 16" fill="currentColor"><path d="M4 6l4 4 4-4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </div>
            <div class="flex items-center gap-1">
                 <svg class="w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
            </div>
        </div>

        <!-- Quick Actions -->
        <div class="px-3 py-2">
            <button class="w-full bg-white border border-gray-200 rounded-md py-1.5 px-3 text-gray-600 font-medium text-left shadow-sm flex items-center gap-2 hover:bg-gray-50">
                <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
                Add context
                <span class="ml-auto text-xs text-gray-400">⌘K</span>
            </button>
        </div>

        <!-- Navigation -->
        <div class="flex-1 overflow-y-auto px-2 py-1 space-y-6">
            <!-- Main Links -->
            <div class="space-y-0.5">
                <div class="flex items-center gap-2 px-2 py-1 rounded-md bg-gray-200/50 text-gray-900 font-medium">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
                    Overview
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/></svg>
                    Team Members
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
                    Recent Activity
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
                    Reviews
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg>
                    Goals
                </div>
            </div>

            <!-- Quick Access -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Quick Access</div>
                <div class="space-y-0.5">
                    {#each favorites as fav}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            {#if fav.icon === 'user'}
                                <div class="w-4 h-4 rounded-full bg-gray-300"></div>
                            {:else if fav.icon === 'team'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                            {:else}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/></svg>
                            {/if}
                            <span class="truncate">{fav.name}</span>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Teams -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Teams</div>
                <div class="space-y-0.5">
                    {#each channels as channel}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            <span class="text-gray-400">#</span>
                            <span class="truncate">{channel.name}</span>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col bg-white min-w-0">
        <!-- Header -->
        <div class="px-8 py-6 pb-2">
            <h2 class="text-2xl font-bold text-gray-900 mb-4">Team Activity</h2>
            <div class="flex items-center justify-between border-b border-gray-100 pb-0">
                <div class="flex gap-6">
                    <button class="pb-2 border-b-2 border-black font-medium text-gray-900">Recent</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">Achievements</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">Growth Areas</button>
                </div>
                <button class="text-gray-400 hover:text-gray-600 mb-2">
                    <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="4" y1="21" x2="4" y2="14"/><line x1="4" y1="10" x2="4" y2="3"/><line x1="12" y1="21" x2="12" y2="12"/><line x1="12" y1="8" x2="12" y2="3"/><line x1="20" y1="21" x2="20" y2="16"/><line x1="20" y1="12" x2="20" y2="3"/><line x1="1" y1="14" x2="7" y2="14"/><line x1="9" y1="8" x2="15" y2="8"/><line x1="17" y1="16" x2="23" y2="16"/></svg>
                </button>
            </div>
        </div>

        <!-- Stats Bar -->
        <div class="px-8 py-3 bg-gray-50 border-y border-gray-100">
            <div class="flex gap-6 text-xs">
                <div class="flex items-center gap-1.5">
                    <span class="text-gray-500">This week:</span>
                    <span class="font-semibold text-gray-900">24 signals captured</span>
                </div>
                <div class="flex items-center gap-1.5">
                    <span class="text-gray-500">Avg per person:</span>
                    <span class="font-semibold text-gray-900">4.2</span>
                </div>
            </div>
        </div>

        <!-- Feed -->
        <div class="flex-1 overflow-y-auto px-8 pb-8">
            <!-- Today -->
            <div class="mb-6">
                <h3 class="text-xs font-medium text-gray-400 mb-3">Today</h3>
                <div class="space-y-4">
                    {#each posts as post}
                        <div class="group flex gap-3 items-start">
                            <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {#if post.icon === 'P'}
                                    <span class="font-serif italic">P</span>
                                {:else}
                                    {post.icon}
                                {/if}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Yesterday -->
            <div>
                <h3 class="text-xs font-medium text-gray-400 mb-3">Yesterday</h3>
                <div class="space-y-4">
                    {#each yesterdayPosts as post}
                        <div class="group flex gap-3 items-start">
                             <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {post.icon}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Right Sidebar -->
    <div class="w-64 border-l border-gray-200 bg-gray-50 flex flex-col flex-shrink-0">
        <div class="p-3">
             <div class="relative">
                <svg class="absolute left-2.5 top-2 w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                <input type="text" placeholder="Search people..." class="w-full bg-white border border-gray-200 rounded-md pl-9 pr-3 py-1.5 text-sm placeholder-gray-400 focus:outline-none focus:border-gray-300" />
            </div>
        </div>

        <div class="flex-1 overflow-y-auto px-3 py-2">
            <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/></svg>
                Team Members
            </div>
            
            <div class="space-y-3">
                {#each team as member}
                    <div class="flex items-start gap-2">
                        <div class="relative">
                            <img src={member.img} alt={member.name} class="w-8 h-8 rounded-full bg-gray-200" />
                            {#if member.online}
                                <div class="absolute -bottom-0.5 -right-0.5 w-2.5 h-2.5 bg-green-500 border-2 border-gray-50 rounded-full"></div>
                            {/if}
                        </div>
                        <div class="flex-1 min-w-0">
                            <div class="text-sm font-medium text-gray-900 truncate">{member.name}</div>
                            {#if member.status}
                                <div class="text-xs text-gray-500 truncate">{member.status}</div>
                            {/if}
                            {#if member.performance}
                                <div class="text-[10px] font-medium mt-0.5">
                                    {#if member.performance === 'Exceeding'}
                                        <span class="text-green-600">● {member.performance}</span>
                                    {:else}
                                        <span class="text-gray-500">● {member.performance}</span>
                                    {/if}
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>

             <div class="mt-6">
                <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                    <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
                    Upcoming Reviews
                </div>
                <div class="text-xs text-gray-600 px-2">
                    Q4 Reviews in 3 weeks
                </div>
            </div>
        </div>
    </div>
</div>
