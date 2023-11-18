combination of [[li fork]] and [[li exec]] is often used creating and child [[li process]] that is executing something


Gewöhnlich werden aber nicht gleich das Daten-, das Stacksegment und der Heap kopiert. 
Denn nicht selten wird ein Kindprozess erzeugt und mit einer Überlagerung eines exec-Funktionsaufrufes mit anderweitigen Daten und Code versorgt. Daher wird häufig im Kernel das Copy on write-Verfahren angewandt. Das bedeutet, dass erst dann wirklich eine Kopie einer Page der Datensegmente erfolgt, wenn in diese geschrieben wird. Dadurch erspart man sich häufig zeitaufwändiges Kopieren, was bei knappem RAM zum Swapping führen kann.


![[li fork#li fork fork]]

![[li exec#li exec exec]]