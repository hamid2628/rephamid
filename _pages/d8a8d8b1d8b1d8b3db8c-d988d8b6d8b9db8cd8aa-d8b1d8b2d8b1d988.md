---
ID: 147
post_title: بررسی وضعیت رزرو
author: iransarsy
post_excerpt: ""
layout: page
permalink: 'http://travel-to-iran-sarsy.com/%d8%a8%d8%b1%d8%b1%d8%b3%db%8c-%d9%88%d8%b6%d8%b9%db%8c%d8%aa-%d8%b1%d8%b2%d8%b1%d9%88/'
published: true
post_date: 2018-06-27 03:58:55
---
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC1" class="blob-code blob-code-inner js-file-line"><span class="pl-pse">&lt;?php</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC2" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c">/**</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC3" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * WooCommerce Bookings Availability Search</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC4" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> *</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC5" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * This is almost pseudo code, it only serves to explain the "how to do it" and does not attempt to be "The Way" to do it.</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC6" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * NOTE: This NEEDS to be refined in order to work as expected.</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC7" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * </span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC8" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * <span class="pl-k">@author</span> António Pinto &lt;apinto@vanguardly.com&gt;</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC9" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * <span class="pl-k">@license</span> http://opensource.org/licenses/gpl-license.php GNU Public License</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC10" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * </span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC11" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * <span class="pl-k">@var</span> string $bookStart (example: '2016-06-14 16:23:00')</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC12" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> * <span class="pl-k">@var</span> string $bookEnd (example: '2016-06-14 16:23:00')</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC13" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c"> */</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC14" class="blob-code blob-code-inner js-file-line"></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC15" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c">// Creating DateTime() objects from the input data.</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC16" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-smi">$dateTimeStart</span> <span class="pl-k">=</span> <span class="pl-k">new</span> <span class="pl-c1">DateTime</span>(<span class="pl-smi">$bookStart</span>);</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC17" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-smi">$dateTimeEnd</span> <span class="pl-k">=</span> <span class="pl-k">new</span> <span class="pl-c1">DateTime</span>(<span class="pl-smi">$bookEnd</span>);</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC18" class="blob-code blob-code-inner js-file-line"></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC19" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c">// Get all Bookings in Range</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC20" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-smi">$bookings</span> <span class="pl-k">=</span> <span class="pl-c1">WC_Bookings_Controller</span><span class="pl-k">::</span>get_bookings_in_date_range(</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC21" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-smi">$dateTimeStart</span><span class="pl-k">-&gt;</span>getTimestamp(),</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC22" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-smi">$dateTimeEnd</span><span class="pl-k">-&gt;</span>getTimestamp(),</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC23" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-s"><span class="pl-pds">'</span><span class="pl-pds">'</span></span>,</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC24" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-c1">false</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC25" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> );</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC26" class="blob-code blob-code-inner js-file-line"></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC27" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c">// Build Array of all the Booked Products for the given Date-Time interval.</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC28" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-smi">$exclude</span>[] <span class="pl-k">=</span> <span class="pl-c1">0</span>;</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC29" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-k">foreach</span> (<span class="pl-smi">$bookings</span> <span class="pl-k">as</span> <span class="pl-smi">$booking</span>) {</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC30" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-smi">$exclude</span>[] <span class="pl-k">=</span> <span class="pl-smi">$booking</span><span class="pl-k">-&gt;</span><span class="pl-smi">product_id</span>;</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC31" class="blob-code blob-code-inner js-file-line"><span class="pl-s1">}</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC32" class="blob-code blob-code-inner js-file-line"></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC33" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-c">// Do a regular WP_Query using 'post__not_in' with the previous array.</span></span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC34" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"><span class="pl-smi">$args</span> <span class="pl-k">=</span> <span class="pl-k">array</span> (</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC35" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-s"><span class="pl-pds">'</span>post__not_in<span class="pl-pds">'</span></span> <span class="pl-k">=&gt;</span> <span class="pl-smi">$exclude</span>,</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC36" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-s"><span class="pl-pds">'</span>post_type<span class="pl-pds">'</span></span> <span class="pl-k">=&gt;</span> [<span class="pl-s"><span class="pl-pds">'</span>product<span class="pl-pds">'</span></span>],</span></td>
</tr>
</tbody>
</table>
<table class="highlight tab-size js-file-line-container" data-tab-size="8">
<tbody>
<tr>
<td id="file-wc-bookings-availability-search-php-LC37" class="blob-code blob-code-inner js-file-line"><span class="pl-s1"> <span class="pl-s"><span class="pl-pds">'</span>post_status<span class="pl-pds">'</span></span> <span class="pl-k">=&gt;</span> [<span class="pl-s"><span class="pl-pds">'</span>published<span class="pl-pds">'</span></span>],</span></td>
</tr>
</tbody>
</table>
<p dir="ltr"><span class="pl-s1">);</span></p>
&nbsp;