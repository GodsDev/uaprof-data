# uaprof-data
Pre-downloaded UA Profiles

/data/http_ tree according to the expected URL.

/data/uaprof directory is UAProf repository, where names of files are md5($uaprofUrl)

/data/uaprofcustomized directory is the repository of *customized* or *corrected* UA Profiles and app looks there if the status of uaprof == 2.
If the customized UAProf is still invalid, the status changes to 9.

While uaprofcustomized directory should be migrated as it is *customized*, the uaprof directory is *only a cache*. But it is recommended to migrate it as well, since the naming is unique and app does not bother to re-download UAProf if it is already on the filesystem. 

If the UAProf files are not available but the list of UAProf URL is available, then a re-initiation of UAProf local repository is recommended by calling:
http://localhost:8080/godsdev/default/montreal/services/defaultdevice/src/init-uaprofs.php .

Directory uaprof_unavailable is a directory for temporary files. Always recreatable by admin-check-timeout.php .
It contains md5(url) files (stubs) with url as its content in order to ease manual creation of md5(url) files for directory uaprofcustomized .
It is recommended to flush the directory and recreate it by admin-check-timeout.php script because some files might be downloaded after the stub was originally created.

