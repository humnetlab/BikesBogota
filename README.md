# BikesBogota
A data science framework for planning the growth of bicycle infrastructures

This repository contains code sufficient to replicate all findings from "A data science framework for planning the growth of
bicycle infrastructures" an in-submission paper on using novel data sources, tools, and methods to identify and prioritize locations where to intervene via properly planned cycling infrastructure.

Some details:

    nodes_all_trips.csv and links_after_rejection.scv are the ODs used as potential demand. These are a filtered version afthe the rejection sampling method described in the paper. The original data was the result from a previous work (​Florez et al., 2017​)

    step_1_parse_trajectories.ipynb parses raw GPS data of the BIKO app.

    step_2_filter_mapmatch.ipynb obtains the map matching for the above GPS data. It parses the trajectories, analyzes the travel speed and duration as well as the departures of each trip. We define our potential demand as all the trips that reproduce the same travel distance than the observed in the BIKO app.

    step3_potential_demand.ipynb calculates the shortest path between nodes from our Potential Demand. As inputs, it uses nodes_all_trips and links_after_rejection csv files. It also generates the flow network in the OSM network which corresponds to the file pair_potential_bike20190401.csv

    step4_percolation.ipynb perform the percolation on a network made up by (1) potential flow network + (2) the existed bikepaths in Bogota.

    step_5_identify_bike_faciliites.ipynb after getting the final network it determines which edges do not have an existing or projected bicycle facility on them

    The latter file communities_table.ipynb is the notebook to generate the figure 7 from the paper.

References:
Florez, M.A., Jiang, S., Li, R., Mojica, C.H., Rios, R.A., Gonz ́alez, M.C., 2017.Measuring the impacts of economic well being in commuting networks - A casestudy of Bogota, Colombia, in:  The 96th Annual Meeting of TransportationResearch Board (TRB), Washington, DC. pp. 1–18. Paper Number 17-05211
