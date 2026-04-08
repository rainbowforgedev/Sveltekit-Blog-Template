<script lang="ts">
	import type { Post } from '$lib/content';

	import FormattedDate from './FormattedDate.svelte';

	interface Props {
		post: Post;
	}

	let { post }: Props = $props();
</script>

<a
	href={post.relativeURL}
	class="group mx-2 flex flex-col-reverse justify-between gap-3 border px-6 py-5 md:flex-row"
>
	<div class="flex flex-col gap-2">
		<div class="text-xs text-secondary-content"><FormattedDate date={post.pubDate} /></div>
		<div
			class="line-clamp-2 text-2xl font-semibold wrap-anywhere text-primary-content group-hover:underline"
		>
			{post.title}
		</div>
		<div class="line-clamp-2 wrap-anywhere text-primary-content/50">{post.description}</div>
	</div>
	<figure class="shrink-0">
		<img
			class="h-32 w-94 scale-100 object-cover duration-100 ease-in group-hover:scale-105 md:w-64"
			src={post.heroImage}
			alt={post.title}
		/>
	</figure>
</a>
