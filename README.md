# GlobalFoodAllocationModel
Two stage Stochastic allocation model for food supply chain networks
End-to-end pipeline for model
(0) Extract cleaned data for each food product in each year 
   - In this case clean data saved as csv (eg 'coffee_clean.csv)   located in Stochastic_problem/test folder
(1) Create Dat files: still in Stochastic_problem/test folder
   - latest version: create_dat_files_two_stage_model_V1
   - inputs: clean_data (eg 'coffee_clean.csv'), 
   - intermediate products which are not saved to csv
        - top_suppliers ( index and country name)
        - df: dataframe of country, sub_region, demand, supply,  etc
   - outputs:
         - scenario dat files
            1. scenarios using all nodes ( saved to scens_all_nodes)
            or 2. scenarios using top 25% suppliers  ( saved to scens_top_suppliers)
        
         - nodes.csv
   
   - this step consist of reading in data
   
(2) a.  Evolution of risk with num scenarios
run stochactic optimization pipeline (Stochastic_two_stage_V2.ipynb): Stochastic_problem/stochastic folder using scenarios_top_suppliers( scenarios generated from upper 25 quartile of supplier). 

    - Run risk neutral model and plot time vs num scenarios
    - Run risk averse model and plot time vs num scenarios
b. Individual scenario analysis
Run Stochastic_two_stage_V1.ipynb(using 1 scenario and deterministic scenario, with no disruption)

    
(3) plotsandViz.ipynb ( generate plots)  located in Stochastic_problem/stochastic folder


(4) world_map_suppliers.ipynb in  Stochastic_problem folder
     - market share of top 5 suppliers
     - world map of suppliers divided by tiers
