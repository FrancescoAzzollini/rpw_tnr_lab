# rpw_tnr_lab
Jupyter notebook for reading and analysing RPW tnr data

Select a date, a start and end for the time range you want to analyse and the path for the cdf file of that day. The header has all the information you need on the functions used in the class and can be accessed with (here I use some example inputs):

my_data = rpw_tnr_lab('2021-10-28', '15:00:00', '16:00:00', 'smooth', 'RPW_plotting\solo_L2_rpw-hfr-surv-cdag_20211028_V05') my_data.header()

It will tell you the modules you need to import and what class functions you can access:

Import the following modules:

Import the following modules:
        
        import matplotlib.pyplot as plt
        from spacepy import pycdf
        import numpy as np
        import matplotlib.dates as mdates
        import math
        import datetime as dt
        from datetime import datetime, timedelta
        from matplotlib.axis import Axis
        from matplotlib.pyplot import cm
        from itertools import compress
        
        Example:
        my_data = rpw_tnr_lab('2021-10-28', '15:00:00', '18:00:00', 'smooth', 'RPW_plotting\\solo_L2_rpw-tnr-surv-cdag_20210921_V08')
        
        'smooth' combines all available sensirs
        'rough' selects the most active sensor throughout the day
        
        my_data.data()['frequencies']
        >>> frequency array in Hz
        my_data.data()['time']
        >>> time array
        my_data.data()['l2_spectrum']
        >>> dynamic spectrum in V^2/Hz
        
        my_data.plot("tnr_dynamic_spectrum\\non_cal\\")
        >>> plots the dynamic spectrum in dB and saves it as 'hfr_dynspec_noncal_date.png' in the path you indicate
