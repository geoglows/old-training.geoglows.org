GEOGloWS ECMWF Streamflow Model
===============================

The GEOGloWS ECMWF Streamflow Model is a Hydrologic Model which provides forecasted and historically simulated river discharge.
The model is built so that it can be accessed through web services, an approach we call Hydrologic Modeling as a Service
(HMaaS). This approach centralizes the cyber-infrastructure, human capacity, and other components of hydrological modeling
using the best meteorology and expertise from ECMWF, along with the latest advances in Information and Communication Technology
(ICT). It is a reliable hydrological forecast information service, a disruptive technology that moves away from needing to
replicate the modelling process, duplicate the underlying geographic and meteorology data, and provide computer, human, and
financial resources locally.

The tools available for accessing the model include a web app, a data service (REST API), a mapping service (ESRI Living Atlas),
and Python package. We provide several example apps, code notebooks, presentations, workshops, and videos to help you learn how
you can access model data, visualize results, and download hydrological information for your location and develop custom workflows
and apps for your decision-making needs. Further, information about how to validate and improve the information based on local
observations is also given.

|geosymposium_video|

.. |geosymposium_video| raw:: html

   <iframe width="1120" height="630" src="https://www.youtube.com/embed/j-RLPVJ_v_0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


To open the app, please visit: `<https://apps.geoglows.org/apps/geoglows-hydroviewer/>`_

.. toctree::
   :maxdepth: 1
   :caption: Workshops:

   streamflow-model/model-components
   streamflow-model/data-service
   streamflow-model/mapping-service
   streamflow-model/geoglows-hydroviewer
   streamflow-model/geoglows-python-package
   streamflow-model/historical-validation
   streamflow-model/forecast-skill-evaluation
   streamflow-model/bias-correction

