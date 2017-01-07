# AndroBugs Framework

AndroBugs Framework is an Android vulnerability analysis system that helps developers or hackers find potential security vulnerabilities in Android applications. 
No splendid GUI interface, but the most efficient (less than 2 minutes per scan in average) and more accurate.

Version: 1.0.0

####Features:####

- Find security vulnerabilities in Android apps
- Check if the code is missing best practices
- Check dangerous shell commands (e.g. "su")
- Collect information from millions of apps
- Check the app’s security protection (marked as ```<Hacker>```, designed for app repackaging hacking)


##Author

- Yu-Cheng Lin  (androbugs.framework at gmail.com, @AndroBugs)


## Usage of Massive Analysis Tools for Unix/Linux

**Prerequisite: Setup MongoDB and configure your own MongoDB settings in "androbugs-db.cfg"**

####To run the massive analysis for AndroBugs Framework:####

```
python AndroBugs_MassiveAnalysis.py -b [Your_Analysis_Number] -t [Your_Analysis_Tag] -d [APKs input directory] -o [Report output directory]
```
 
Example:
```
python AndroBugs_MassiveAnalysis.py -b 20151112 -t BlackHat -d ~/All_Your_Apps/ -o ~/Massive_Analysis_Reports
```


####To get the summary report and all the vectors of massive analysis:####

```
python AndroBugs_ReportSummary.py -m massive -b [Your_Analysis_Number] -t [Your_Analysis_Tag]
```

Example:
```
python AndroBugs_ReportSummary.py -m massive -b 20151112 -t BlackHat
```


####To list the potentially vulnerable apps by Vector ID and Severity Level (Log Level):####

```
python AndroBugs_ReportByVectorKey.py -v [Vector ID] -l [Log Level] -b [Your_Analysis_Number] -t [Your_Analysis_Tag]
python AndroBugs_ReportByVectorKey.py -v [Vector ID] -l [Log Level] -b [Your_Analysis_Number] -t [Your_Analysis_Tag] -a
```

Example:
```
python AndroBugs_ReportByVectorKey.py -v WEBVIEW_RCE -l Critical -b 20151112 -t BlackHat
python AndroBugs_ReportByVectorKey.py -v WEBVIEW_RCE -l Critical -b 20151112 -t BlackHat -a
```

##Requirements

- Python 2.7.x (Python 3.X not supported at the moment)
- [PyMongo library](http://api.mongodb.org/python/current/installation.html) (If you want to use the massive analysis tool)

##Licenses

* AndroBugs Framework is under the license of [GNU GPL v3.0](http://www.gnu.org/licenses/gpl-3.0.txt)

