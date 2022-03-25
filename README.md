Клеточная линия: HepG2

Список гистоновых меток:

H2az	Hepg2H2azStdAlnRep1.bam	

H3k04me1	Hepg2H3k04me1StdAlnRep1.bam	

H3k09me3	Hepg2H3k09me3AlnRep1.bam	

H3k4me2	Hepg2H3k4me2StdAlnRep1.bam	

H3k9ac	Hepg2H3k9acStdAlnRep1.bam	

H3k27ac	Hepg2H3k27acStdAlnRep1.bam	

H3k27me3	Hepg2H3k27me3StdAlnRep1.bam	

H3k36me3	Hepg2H3k36me3StdAlnRep1.bam	

H3k79me2	Hepg2H3k79me2StdAlnRep1.bam	

H4k20me1	Hepg2H4k20me1StdAlnRep1.bam	


Контроль: Hepg2ControlStdAlnRep1.bam

Рисунки из выдачи ChromHMM:

![emissions_10](https://user-images.githubusercontent.com/72361668/160193174-bf8213b7-0dbe-4c23-aa1e-98f71eff9893.png)
![Hepg2_10_overlap](https://user-images.githubusercontent.com/72361668/160193191-907856b5-16a9-406e-a7d7-243afa6cd491.png)
![Hepg2_10_RefSeqTES_neighborhood](https://user-images.githubusercontent.com/72361668/160193198-e18c5ac8-f6e4-4550-a584-0c14db3513ef.png)
![Hepg2_10_RefSeqTSS_neighborhood](https://user-images.githubusercontent.com/72361668/160193204-1edaf769-1a3e-4b9f-bf64-b1a9205b30d3.png)
![transitions_10](https://user-images.githubusercontent.com/72361668/160193219-e78353f8-f78b-4e9e-adae-697140e9c365.png)


Список команд:

Установака:

!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/fix-colab-gpu.sh && bash fix-colab-gpu.sh

!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/colab_build.sh && bash colab_build.sh

!java --list-modules | grep "jdk.jshell"

! wget http://compbio.mit.edu/ChromHMM/ChromHMM.zip

!unzip /content/ChromHMM.zip

Скачивание файлов:

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H2azStdAlnRep1.bam -O Hepg2H2azStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k04me1StdAlnRep1.bam -O Hepg2H3k04me1StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k09me3AlnRep1.bam -O Hepg2H3k09me3AlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k4me2StdAlnRep1.bam -O Hepg2H3k4me2StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k9acStdAlnRep1.bam -O Hepg2H3k9acStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k27acStdAlnRep1.bam -O Hepg2H3k27acStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k27me3StdAlnRep1.bam -O Hepg2H3k27me3StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k36me3StdAlnRep1.bam -O Hepg2H3k36me3StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k79me2StdAlnRep1.bam -O Hepg2H3k79me2StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H4k20me1StdAlnRep1.bam -O Hepg2H4k20me1StdAlnRep1.bam

#control

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2ControlStdAlnRep1.bam -O Hepg2ControlStdAlnRep1.bam

ChromHMM:

!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt   binarizedData

from google.colab import drive

drive.mount('/content/drive')

!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel  -b 200 binarizedData /content/drive/MyDrive/hw_HMM 10 hg19
