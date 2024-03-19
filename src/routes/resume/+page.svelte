<script lang="ts">
	import resume from '$lib/documents/Ethan Davila Resume.pdf';
</script>

<a href={resume} download>
	<p style="text-align: center;">Download</p>
</a>

<section class="section">
	<object data={resume} type="application/pdf" width="100%" height="1000px">
		<p>
			Unable to display PDF file. <a href={resume}>Download</a> instead.
		</p>
	</object>
</section>
