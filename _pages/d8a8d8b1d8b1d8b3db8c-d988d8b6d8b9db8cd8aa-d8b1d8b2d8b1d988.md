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
<?php
/**
* WooCommerce Bookings Availability Search
*
* This is almost pseudo code, it only serves to explain the "how to do it" and does not attempt to be "The Way" to do it.
* NOTE: This NEEDS to be refined in order to work as expected.
*
* @author António Pinto <apinto@vanguardly.com>
* @license http://opensource.org/licenses/gpl-license.php GNU Public License
*
* @var string $bookStart (example: '2016-06-14 16:23:00')
* @var string $bookEnd (example: '2016-06-14 16:23:00')
*/

// Creating DateTime() objects from the input data.
$dateTimeStart = new DateTime($bookStart);
$dateTimeEnd = new DateTime($bookEnd);

// Get all Bookings in Range
$bookings = WC_Bookings_Controller::get_bookings_in_date_range(
$dateTimeStart->getTimestamp(),
$dateTimeEnd->getTimestamp(),
'',
false
);

// Build Array of all the Booked Products for the given Date-Time interval.
$exclude[] = 0;
foreach ($bookings as $booking) {
$exclude[] = $booking->product_id;
}

// Do a regular WP_Query using 'post__not_in' with the previous array.
$args = array (
'post__not_in' => $exclude,
'post_type' => ['product'],
'post_status' => ['published'],

);