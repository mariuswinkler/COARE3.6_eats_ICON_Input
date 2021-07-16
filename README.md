# pyCOARE
Initial Python implementation of COARE air/sea flux algorithms developed at NOAA Physical Sciences Lab. 

The COARE model followed from the international TOGA-COARE field program which took place in the western Pacific warm pool over 4 months from November 1992 to February 1993 (Fairall et al. 1996).  The algorithm is intended to provide estimates of momentum, sensible heat, and latent heat fluxes using inputs of bull atmospheric variables (wind speed, SST, air temperature, air humidity).  The algorithm contains subroutines to deal with near-surface gradients of temperature in the ocean.  Version 2.5 was published in 1996 and a major update, version 3.0 was published in 2003.  This update was based on new observations at higher wind speeds (10 to 20 m/s).  Version 3.5 was released in 2013 following the publication of Edson et al. 2013, which made adjustments to the wind speed dependence of the Charnock parameter based on a large data base of direct covariance stress observations (principally from a buoy).  This led to an increase in stress for wind speeds greater than about 18 m/s.  The roughness Reynolds number formulation of the scalar roughness length was tuned slightly to give the same values of Ch and Ce as version 3.0.  The diurnal warm layer model was structured as a separate routine instead of embedded in a driver program.  COARE 3.5 was based on Edson’s buoy data (Edson et al. 2013) and was compared to a large data base (a total of 16,000 hours of observations) combining observations from NOAA, WHOI, and U. Miami (Fairall et al. 2011).

The PYTHON program given here is for version 3.5.  There is a new matlab set, version 3.6.  This new version is restructured slightly and the main advance is improved wave parameterizations and treatment of wave breaking for the gas transfer aspects (COAREG).  The windspeed only representation is the same as 3.5.

More details are found in coare3.6_readme_1.docx

The python code runs the same data set used to exercise the matlab code. Execute '%run coare35vn.py' from the iPython command line for test run with 'test_35_data.txt' input data file. Edit line 554 to indicate path to test data file. This will output a file of results that you can compare to the test_35_output_py_082020.txt provided.  The file contains a time series of flux variables (usr	tau	hsb	hlb	hlwebb	tsr	qsr	zot	zoq	Cd	Ch	Ce	L	zet	dter	dqer	tkt	RF	Cdn_10	Chn_10	Cen_10 ).

References:
- Edson, J.B., J. V. S. Raju, R.A. Weller, S. Bigorre, A. Plueddemann, C.W. Fairall, S. Miller, L. Mahrt, Dean Vickers, and Hans Hersbach, 2013: On the Exchange of momentum over the open ocean. J. Phys. Oceanogr., 43, 1589–1610. doi: http://dx.doi.org/10.1175/JPO-D-12-0173.1 
- Fairall, C.W., E.F. Bradley, J.S. Godfrey, G.A. Wick, J.B. Edson, and G.S. Young, 1996a: The cool skin and the warm layer in bulk flux calculations. J. Geophys. Res. 101, 1295-1308.
- Fairall, C.W., E.F. Bradley, D.P. Rogers, J.B. Edson, G.S. Young, 1996b: Bulk parameterization of air-sea fluxes for TOGA COARE. J. Geophys. Res. 101, 3747-3764.
- Fairall, C.W., E.F. Bradley, J.E. Hare, A.A. Grachev, and J.B. Edson, 2003: Bulk parameterization of air-sea fluxes: Updates and verification for the COARE algorithm.   J. Climate 16, 571-591.
- Fairall, C.W., Mingxi Yang, Ludovic Bariteau, J.B. Edson, D. Helmig, W. McGillis, S. Pezoa, J.E. Hare, B. Huebert, and B. Blomquist, 2011: Implementation of the COARE flux algorithm with CO2, DMS, and O3.  J. Geophys. Res., 116, C00F09, doi:10.1029/2010JC006884.

