# MFSUD – Instances

This repository stores the instances used in the paper entitled `Robust Policies for a Multi-Period Fleet Sizing Problem under Demand Uncertainty` by Alice Raffaele, Demetrio Laganà, and Roberto Roberti.

In this repository, there are two benchmark sets:

- `Solomon`, composed of 1800 instances (half with 25 customers and the other half with 50 customers) divided into three subfolders.

	The instance format is the following:

	```
	# <problem_info_char> <num_periods> <num_customers> <num_vehicle_types> <early_penalty> <late_penalty> <vehicle_cost_factor> <\Gamma>
	p 6 25 1 1 2 1000 8 # 6 periods, 25 customers, and 1 vehicle type; each day of early (late) delivery costs 1 (2); 8 future customers can exceed their minimum demand.
	
	# <customer_info_char> <placing_order_day> <inner_day_window_start> <inner_day_window_end> <early_delivery_days> <late_delivery_days> <minimum_demand> <maximum_demand> <actual_demand> 
	i 1 2 3 1 1 40 80 75 # This customer places an order on day d=1; the inner day window is [1+2, 1+3] = [3, 4]; the flexible day window is [1+2-1, 1+3+1] = [2,5]; the minimum, maximum, and actual demands are 40, 80, and 75, respectively.
	... 
	... # 25 rows overall
	
	# <vehicle_type_info_char> <capacity> <cost>
	k 96 1 # All vehicles are homogeneous, each with capacity 96 and cost 1*1000 = 1000
	```
	In particular:
	-  the 450 labeled `Solomon*_0.txt` – `Solomon*_24.txt` are *extreme* instances  (i.e., exactly $\Gamma$ customers require their maximum demand, and, in particular, `Solomon*_0.txt` – `Solomon*_4.txt` are *very extreme*, in the sense that they ask for service on the same day);
	- the 1350 labeled `Solomon*_25.txt` – `Solomon*_100.txt` are just *sampled* instances (i.e., at most $\Gamma$ customers exceed their minimum demand not on the same day).

	
- `Industrial`, composed of 1620 instances (with different numbers of customers in [200, 300]) divided into nine subfolders (one per each value of Gamma and each value of maximum demand).

	The instance format is almost the same as for `Solomon` instances: 
	
	```
	# <problem_info_char> <num_periods> <num_customers> <num_vehicles> <early_penalty> <late_penalty> <vehicle_cost_factor1> <\Gamma>
	
	p 6 271 9 1 2 10000 21 # 6 periods, 25 customers, and 9 vehicles; each day of early (late) delivery costs 1 (2); 21 future customers can exceed their minimum demand.
	
	# <customer_info_char> <placing_order_day> <inner_day_window_start> <inner_day_window_end> <early_delivery_days> <late_delivery_days> <minimum_demand> <maximum_demand> <actual_demand> 
	i 3 1 1 0 1 637 1912 1402 # This customer places an order on day d=3; the inner day window is [3+1, 3+1] = [4, 4]; the flexible day window is [3+1-0, 3+1+1] = [4,5]; the minimum, maximum, and actual demands are 637, 1912, and 1402, respectively.
	...
	... # 271 rows overall
	
	# <vehicle_info_char> <capacity> <vehicle_cost_factor2>
	k 13000 1 # The first vehicle has a capacity of 130000 and costs 1000*1 = 1000
	k 36000 3 # The second vehicle has a capacity of 36000 and costs 1000*3 = 3000 
	...
	... # 9 rows overall
	
	```
	
	In particular:
	-  the 15 labeled `Industrial*_0.txt` – `Industrial*_4.txt` are *extreme* instances  (i.e., exactly $\Gamma$ customers require their maximum demand, and, in particular, `Industrial*_0.txt` are *very extreme*, in the sense that they ask for service on the same day);
	- the 45 labeled `Industrial*_5.txt` – `Industrial*_59.txt` are just *sampled* instances (i.e., at most $\Gamma$ customers exceed their minimum demand not on the same day).

In all instances, the staffing cost is always set to `100`.
	

