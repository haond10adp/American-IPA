<script lang="ts">
	let showNotification = false;
	let notificationText = '';

	function handleTdClick(event: MouseEvent) {
		const td = event.currentTarget as HTMLTableCellElement;
		const ipa = td.querySelector('.IPA');
		if (ipa) {
			const text = ipa.textContent?.trim();
			if (text) {
				navigator.clipboard.writeText(text).then(() => {
					notificationText = `Copied "${text}" to clipboard`;
					showNotification = true;
					td.style.backgroundColor = '#fde68a';
					setTimeout(() => {
						td.style.backgroundColor = '';
					}, 500);
					setTimeout(() => {
						showNotification = false;
					}, 1200);
				});
			}
		}
	}
</script>

<h2>Consonants</h2>
<table>
	<tbody>
		<tr>
			<th colspan="2"></th>
			<th scope="col">Labial</th>
			<th scope="col">Dental</th>
			<th scope="col">Alveolar</th>
			<th scope="col">Post-<br />alveolar</th>
			<th scope="col">Palatal</th>
			<th scope="col">Velar</th>
			<th scope="col">Glottal</th>
		</tr>
		<tr>
			<th colspan="2" scope="row">Nasal</th>
			<td on:click={handleTdClick}><span class="IPA">m</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">n</span></td>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ŋ</span></td>
			<td></td>
		</tr>
		<tr>
			<th rowspan="2" scope="row">Plosive</th>
			<th scope="row"><span style="font-size: 85%">fortis</span></th>
			<td on:click={handleTdClick}><span class="IPA">p</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">t</span></td>
			<td on:click={handleTdClick}><span class="IPA">tʃ</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">k</span></td>
			<td></td>
		</tr>
		<tr>
			<th scope="row"><span style="font-size: 85%">lenis</span></th>
			<td on:click={handleTdClick}><span class="IPA">b</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">d</span></td>
			<td on:click={handleTdClick}><span class="IPA">dʒ</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ɡ</span></td>
			<td></td>
		</tr>
		<tr>
			<th rowspan="2" scope="row">Fricative</th>
			<th scope="row"><span style="font-size: 85%">fortis</span></th>
			<td on:click={handleTdClick}><span class="IPA">f</span></td>
			<td on:click={handleTdClick}><span class="IPA">θ</span></td>
			<td on:click={handleTdClick}><span class="IPA">s</span></td>
			<td on:click={handleTdClick}><span class="IPA">ʃ</span></td>
			<td></td>
			<td on:click={handleTdClick}>(<span class="IPA">x</span>)</td>
			<td rowspan="2" scope="row" on:click={handleTdClick}><span class="IPA">h</span></td>
		</tr>
		<tr>
			<th scope="row"><span style="font-size: 85%">lenis</span></th>
			<td on:click={handleTdClick}><span class="IPA">v</span></td>
			<td on:click={handleTdClick}><span class="IPA">ð</span></td>
			<td on:click={handleTdClick}><span class="IPA">z</span></td>
			<td on:click={handleTdClick}><span class="IPA">ʒ</span></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<th colspan="2" scope="row">Approximant</th>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">l</span></td>
			<td on:click={handleTdClick}><span class="IPA">r</span></td>
			<td on:click={handleTdClick}><span class="IPA">j</span></td>
			<td on:click={handleTdClick}><span class="IPA">w</span></td>
			<td></td>
		</tr>
	</tbody>
</table>

<h2>Vowels</h2>
<table>
	<caption>General American</caption>
	<tbody>
		<tr>
			<th rowspan="2"></th>
			<th colspan="2">Front</th>
			<th colspan="2">Central</th>
			<th colspan="2">Back</th>
		</tr>
		<tr>
			<th><span style="font-size: 85%">lax</span></th>
			<th><span style="font-size: 85%">tense</span></th>
			<th><span style="font-size: 85%">lax</span></th>
			<th><span style="font-size: 85%">tense</span></th>
			<th><span style="font-size: 85%">lax</span></th>
			<th><span style="font-size: 85%">tense</span></th>
		</tr>
		<tr>
			<th>Close</th>
			<td on:click={handleTdClick}><span class="IPA">ɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">i</span></td>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ʊ</span></td>
			<td on:click={handleTdClick}><span class="IPA">u</span></td>
		</tr>
		<tr>
			<th>Mid</th>
			<td on:click={handleTdClick}><span class="IPA">ɛ</span></td>
			<td on:click={handleTdClick}><span class="IPA">eɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">ə</span></td>
			<td on:click={handleTdClick}>(<span class="IPA">ɜ</span>)</td>
			<td on:click={handleTdClick}>(<span class="IPA">ʌ</span>)</td>
			<td on:click={handleTdClick}><span class="IPA">oʊ</span></td>
		</tr>
		<tr>
			<th>Open</th>
			<td on:click={handleTdClick}><span class="IPA">æ</span></td>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ɑ</span></td>
			<td></td>
			<td on:click={handleTdClick}>(<span class="IPA">ɔ</span>)</td>
		</tr>
	</tbody>
</table>

<table>
	<tbody>
		<tr>
			<th>Diphthong</th>
			<td on:click={handleTdClick}><span class="IPA">aɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">ɔɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">aʊ</span></td>
		</tr>
	</tbody>
</table>

<table>
	<caption>Received Pronunciation</caption>
	<tbody>
		<tr>
			<th rowspan="3"></th>
			<th rowspan="2" colspan="2">Front</th>
			<th rowspan="2" colspan="2">Central</th>
			<th colspan="4">Back</th>
		</tr>
		<tr>
			<th colspan="2"><span style="font-size: 85%">unrounded</span></th>
			<th colspan="2"><span style="font-size: 85%">rounded</span></th>
		</tr>
		<tr>
			<th><span style="font-size: 85%">short</span></th>
			<th><span style="font-size: 85%">long</span></th>
			<th><span style="font-size: 85%">short</span></th>
			<th><span style="font-size: 85%">long</span></th>
			<th><span style="font-size: 85%">short</span></th>
			<th><span style="font-size: 85%">long</span></th>
			<th><span style="font-size: 85%">short</span></th>
			<th><span style="font-size: 85%">long</span></th>
		</tr>
		<tr>
			<th>Close</th>
			<td on:click={handleTdClick}><span class="IPA">ɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">iː</span></td>
			<td on:click={handleTdClick}><span class="IPA">ʊ</span></td>
			<td on:click={handleTdClick}><span class="IPA">uː</span></td>
			<td></td>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ɔː</span></td>
		</tr>
		<tr>
			<th>Mid</th>
			<td on:click={handleTdClick}><span class="IPA">e</span></td>
			<td on:click={handleTdClick}><span class="IPA">ɛː</span></td>
			<td on:click={handleTdClick}><span class="IPA">ə</span></td>
			<td on:click={handleTdClick}><span class="IPA">ɜː</span></td>
			<td on:click={handleTdClick}><span class="IPA">ʌ</span></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ɒ</span></td>
			<td></td>
		</tr>
		<tr>
			<th>Open</th>
			<td on:click={handleTdClick}><span class="IPA">æ</span></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td on:click={handleTdClick}><span class="IPA">ɑː</span></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>

<table>
	<tbody>
		<tr>
			<th>Diphthongs</th>
			<td on:click={handleTdClick}><span class="IPA">eɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">aɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">ɔɪ</span></td>
			<td on:click={handleTdClick}><span class="IPA">aʊ</span></td>
			<td on:click={handleTdClick}><span class="IPA">əʊ</span></td>
			<td on:click={handleTdClick}><span class="IPA">ɪə</span></td>
			<td on:click={handleTdClick}><span class="IPA">ʊə</span></td>
		</tr>
	</tbody>
</table>

<table>
	<tbody>
		<tr>
			<th>Triphthongs</th>
			<td on:click={handleTdClick}><span class="IPA">(eɪə)</span></td>
			<td on:click={handleTdClick}><span class="IPA">(aɪə)</span></td>
			<td on:click={handleTdClick}><span class="IPA">(ɔɪə)</span></td>
			<td on:click={handleTdClick}><span class="IPA">(aʊə)</span></td>
			<td on:click={handleTdClick}><span class="IPA">(əʊə)</span></td>
		</tr>
	</tbody>
</table>

{#if showNotification}
	<div class="notification">{notificationText}</div>
{/if}

<style>
	table {
		border-collapse: collapse;
		font-size: x-large;
		margin: 24px auto;
		font-family: Arial, sans-serif;
		background: #fafafa;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
	}
	th,
	td {
		border: 1px solid #bbb;
		padding: 8px 14px;
		text-align: center;
		min-width: 48px;
		cursor: pointer;
	}
	th {
		background: #e0e7ef;
		font-weight: bold;
		cursor: default;
	}
	.IPA {
		font-size: 1.25em;
		font-family: 'Charis SIL', 'Doulos SIL', 'Arial', sans-serif;
		color: #2a3a5e;
	}
	tr:nth-child(even) td {
		background: #f3f6fa;
	}
	tr:hover td {
		background: #dbeafe;
	}
	h2 {
		text-align: center;
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		color: #1e40af;
		margin-top: 32px;
	}
	.notification {
		position: fixed;
		top: 24px;
		left: 50%;
		transform: translateX(-50%);
		background: #1e40af;
		color: #fff;
		padding: 12px 32px;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
		font-size: 1.1em;
		z-index: 1000;
		animation: fadein 0.2s;
	}
	@keyframes fadein {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
</style>
