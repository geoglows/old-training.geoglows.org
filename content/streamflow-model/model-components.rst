About the GEOGloWS ECMWF Streamflow Service
===========================================
GEOGloWS helps to organize the international community engaged in the hydrologic sciences, observations, and forecasting.
It provides a forum for government-to-government collaboration, and engagement with the academic and private sectors
to achieve the delivery of actionable water information. Since the formal creation of the initiative in 2017, the most significant
element of GEOGloWS has been the application of Earth Observations (EO) to create a system that forecasts flow on every river of
the world while also providing a 40+ year simulated historical flow. This system is called the GEOGLoWS ECMWF Streamflow Services.

.. image:: /_static/imgs/about-gem/forecasted-and-historical-streamflow.jpg

Daily 15-day ensemble forecast and 40-year historical simulation for every river in the world
---------------------------------------------------------------------------------------------
The GEOGloWS ECMWF Streamflow Service uses a Hydrologic Modeling as a Service (HMaaS) approach, which centralizes the
cyberinfrastructure, human capacity, and other components of hydrologic modeling. It uses the best forecasts and expertise
available, along with the latest advances in Information and Communication Technology. We can now deliver reliable
forecast information as a service, instead of delivering the underlying data, which then must be synthesized and computed locally.

In the past, millions of dollars have been invested by international and local agencies to develop hydrologic models
from global data sources. This approach requires every agency to be able to download input data (e.g., terrain
information, land use, meteorological, and other) to create models, and then have the computational power, software, and
human capacity necessary to run and calibrate those models. Having to replicate this resource everywhere is expensive in
terms of the cyberinfrastructure required. In addition, these systems frequently have short useful life spans because
the organizations who use them lack the resources to continue maintaining and operating them when the external funding
source is depleted.

The GEOGloWS global streamflow forecasting service allows local stakeholders to focus on solving water management
problems such as flooding, drought, and water/food security issues by providing the water intelligence they need to make
decisions. It also benefits the global economy by providing water intelligence to sectors that need to make high-risk
investment decisions such as the insurance and reinsurance industries.

.. image:: /_static/imgs/about-gem/disruptive-technology.jpg

Hydrologic Modeling as a Service (HMaaS)
----------------------------------------
The streamflow services are powered by the cyberinfrastructure at ECMWF by using their ensemble meteorological forecast
through the HTESSEL land surface model to produce global runoff on a 16x16 kilometer grid. This output is then mapped to
the GEOGloWS watersheds and routed through the river network using Muskingum routing, as implemented in the RAPID
software to produce a 15-day forecast on every river. The ERA5 retrospective historical data are run over the same
domain to produce the 40-year record of streamflow that is used to derive return-periods and put the current forecast in
context. Each of the components of the model and many of their results have been studied individually and published in
academic journals, refer to the Publications page for more information on each component.

.. image:: /_static/imgs/about-gem/services-and-apps.jpg

Model Workflow and Components
-----------------------------
Resulting streamflow forecasts, along with a web mapping service produced and hosted by Esri, are constructed and
delivered by an API so that custom web and other applications can be created from the HMaaS.

.. image:: /_static/imgs/about-gem/hydroviewer-with-graph.jpg
