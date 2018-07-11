# ERADAT
Efficient Retrieval and Access to Data Archived on Tape

The Efficient Retrieval and Access to Data Archived on Tape or ERADAT, is a file retrieval scheduler for IBM HPSS. 
ERADAT evolved from the Oak Ridge batch code1 as a prototype, and then modified to fit BNL’s requirements. 
ERADAT has evolved to include many additional features such as dynamic drive usage allocation, support for multiple projects 
and groups, support for multiple drive technologies (9940 and LTO-3 and LTO-4 drive series), request lifetime expiration, 
and multiple staging algorithm including ‘by-demand’ and FIFO. 
ERADAT also keeps all transaction history for performance reporting purposes but the historical usage also helps guiding and 
fine-tuning the system. ERADAT collects additional data from other sources such as library controller, for cross-reference 
checking. ERADAT allows modifying the drive allocation on the fly via a Web-based monitoring system and control interface.

When storing large amounts of data, tape can be substantially cost effective (in terms of the media cost, power consumption, 
and air conditioning cost), compared to modern storage technologies such as hard-disk or other data storage devices. 
Therefore, tape storage is still commonly used in large computer centers, mainly as a high capacity medium for backups and 
archiving.  Randomly restoring files out of tapes destroys access performance to tape by causing too frequently, high latency 
and time consuming tape mount and dismount. BNL’s mass storage system currently holds more than 16 PB of data on tapes, 
managed by HPSS. To restore files from HPSS, we make use of a scheduler software, called ERADAT.

ERADAT is written in C, designed to submit jobs to HPSS via API calls.  It updates all the transactions details to both log 
file and MySQL database.  A Web based monitor is designed to display real-time job status based on the MySQL database.

With ERADAT, we have demonstrated that reading from tape can actually achieve full speed in the tape-drive specification.  For
example: we observed 255 MB/s on T10K-D, 132 MB/s on LTO-5.

ERADAT is the interface between HPSS and other applications such as the DataCarousel, our home developed production system and 
dCache. Scalla/Xrootd MSS can also be interfaced with HPSS via DataCarousel.  ERADAT has demonstrated great performance in BNL.

More details about ERADAT, please see: Journal of Physics: Conference Series 331 (2011) 042045
