# Problem Statement :
One of India's largest logistics company needs to understand and process the data coming out of data engineering pipelines. 
We need to clean, sanitize and manipulate data to get useful features out of raw fields.



# Insights :
- start_scan_to_end_scan has multiple peaks at ~0, 2000, 3000 implying that there are 3 major routes taken by the logisitcs the company
- actual_distance_to_destination also looks like the overlap of 3 poisson distributions (supporting above claim)
- actual_time, osrm_time and osrm_distance shows poisson like distribution
- segment_actual_time, segment_osrm_time and segment_osrm_distance seem to be possion distributed as well with an even lower lambda
- FTL has much higher actual_distance_to_destination and start_scan_to_end_scan than Carting
- Mumbai to Bhiwandi is the busiest corridor followed by city-within trips in bengaluru
- The most busiest source cities are Bengaluru, Gurgaon (~4.5%)
- The most busiest source states are Maharashtra, Karnataka (~13%)
- The most busiest destination cities are Mumbai, Bengaluru (~4.5%)
- The most busiest destination states are Karnataka, Maharashtra (~13%)
- t-test giving HIGH p-value means start_scan_to_end_scan and od_time_diff ARE NOT significantly different
- Welchs t-test giving LOW p-value means actual_time and osrm_time ARE significantly different
- t-test giving HIGH p-value means actual_time and segment_actual_time ARE NOT significantly different
- Welchs t-test giving LOW p-value means osrm_distance and segment_osrm_distance ARE significantly different
- Welchs t-test giving LOW p-value means osrm_time and segment_osrm_time ARE significantly different 



# Recommendations : 
- Most of the companies trips seems to be concentrated around few cities like Gurgaon, Mumbai and Bengaluru. Based on this, I would recommend the logistics company to expand its network to other parts of the country as well.
- The actual time and OSRM time shows significance difference. Based on this I would suggest the company to look closley at the open source time calculator as it might be buggy or not be taking some real life considerations into account. Having an accurate model would help the company in managing its resources better and also would give its customers a more accurate expected time for delivery.