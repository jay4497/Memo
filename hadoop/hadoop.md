<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html><head><title>hadoop.htm</title>
<meta http-equiv="Content-Style-Type" content="text/css">
<style type="text/css"><!--
body {
  margin: 15px 18px 15px 18px;
  background-color: #ffffff;
}
/* ========== Text Styles ========== */
hr { color: #000000}
body, table, span.rvts0 /* Normal text */
{
 font-size: 10pt;
 font-family: '宋体';
 font-style: normal;
 font-weight: normal;
 color: #000000;
 text-decoration: none;
}
a.rvts1, span.rvts1 /* Hyperlink */
{
 color: #0000ff;
 text-decoration: underline;
}
span.rvts2
{
 font-size: 12pt;
 font-family: 'Times New Roman', 'Times', serif;
 font-weight: bold;
}
span.rvts3
{
 font-size: 12pt;
 font-family: 'Courier New', 'Courier', monospace;
 font-weight: bold;
}
span.rvts4
{
 font-size: 12pt;
 font-weight: bold;
}
span.rvts5
{
 font-size: 12pt;
 font-family: 'Times New Roman', 'Times', serif;
}
span.rvts6
{
 font-family: 'Courier New', 'Courier', monospace;
}
span.rvts7
{
 font-size: 12pt;
 font-family: 'Courier New', 'Courier', monospace;
}
span.rvts8
{
 font-size: 12pt;
}
span.rvts9
{
 font-size: 12pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
 font-weight: bold;
}
span.rvts10
{
 font-size: 12pt;
 font-family: '黑体';
 font-weight: bold;
}
span.rvts11
{
 font-size: 14pt;
 font-family: '黑体';
 font-weight: bold;
}
span.rvts12
{
 font-size: 12pt;
 font-family: '黑体';
}
span.rvts13
{
 font-size: 12pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
}
span.rvts14
{
 font-size: 12pt;
 font-family: 'Calibri';
 font-weight: bold;
}
span.rvts15
{
 font-size: 12pt;
 font-family: '等线';
 font-weight: bold;
}
span.rvts16
{
 font-size: 12pt;
 font-family: '等线';
}
a.rvts17, span.rvts17
{
 font-size: 12pt;
 font-family: '等线';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts17:hover { color: #ff0000; }
span.rvts18
{
 font-family: 'Arial', 'Helvetica', sans-serif;
}
a.rvts19, span.rvts19
{
 font-size: 12pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts19:hover { color: #ff0000; }
span.rvts20
{
 font-size: 14pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
}
a.rvts21, span.rvts21
{
 font-size: 14pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts21:hover { color: #ff0000; }
span.rvts22
{
 font-size: 14pt;
 font-family: 'Arial', 'Helvetica', sans-serif;
 font-weight: bold;
}
span.rvts23
{
 font-size: 14pt;
 font-family: '等线';
 font-weight: bold;
}
a.rvts24, span.rvts24
{
 font-size: 14pt;
 font-family: '等线';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts24:hover { color: #ff0000; }
a.rvts25, span.rvts25
{
 font-size: 12pt;
 font-family: '等线';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts25:hover { color: #ff0000; }
span.rvts26
{
 font-family: '等线';
}
span.rvts27
{
 font-size: 12pt;
 font-family: '楷体';
}
a.rvts28, span.rvts28
{
 font-size: 12pt;
 font-family: '楷体';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts29, span.rvts29
{
 font-size: 12pt;
 font-family: 'Times New Roman', 'Times', serif;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts30, span.rvts30
{
 font-size: 12pt;
 font-family: '等线';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts31, span.rvts31
{
 font-size: 12pt;
 font-family: '等线';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
span.rvts32
{
 font-size: 12pt;
 font-family: '等线 Light';
 font-weight: bold;
}
a.rvts33, span.rvts33
{
 font-size: 12pt;
 font-family: '等线 Light';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts34, span.rvts34
{
 font-size: 12pt;
 font-family: '等线 Light';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts35, span.rvts35
{
 font-size: 12pt;
 font-family: '等线 Light';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts35:hover { color: #ff0000; }
span.rvts36
{
 font-size: 14pt;
 font-family: '等线 Light';
 font-weight: bold;
}
a.rvts37, span.rvts37
{
 font-size: 14pt;
 font-family: '等线 Light';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts38, span.rvts38
{
 font-size: 14pt;
 font-family: '等线 Light';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts39, span.rvts39
{
 font-size: 14pt;
 font-family: '等线 Light';
 font-weight: bold;
 color: #0000ff;
 text-decoration: underline;
}
a.rvts39:hover { color: #ff0000; }
span.rvts40
{
 font-size: 12pt;
 font-family: '等线 Light';
}
a.rvts41, span.rvts41
{
 font-size: 12pt;
 font-family: '等线 Light';
 color: #0000ff;
 text-decoration: underline;
}
a.rvts41:hover { color: #ff0000; }
span.rvts42
{
 font-size: 12pt;
 font-family: '等线';
 font-weight: bold;
 color: #ff0000;
}
/* ========== Para Styles ========== */
p,ul,ol /* Paragraph Style */
{
 text-align: left;
 text-indent: 0px;
 padding: 0px 0px 0px 0px;
 margin: 0px 0px 0px 0px;
}
.rvps1 /* Centered */
{
 text-align: center;
}
.rvps2
{
 line-height: 1.50;
}
.rvps3
{
 text-indent: 34px;
}
.rvps4
{
 text-align: right;
}
--></style>
</head>
<body>

<span class=rvts15>1&#12289;&#20851;&#38381;&#38450;&#28779;&#22681;</span>

<span class=rvts15>systemctl stop firewalld</span>

<span class=rvts15>
</span>

<span class=rvts15>2&#12289;&#20462;&#25913;hosts</span>

<span class=rvts15>vi /etc/hosts</span>

<span class=rvts15>192.168.19.128 master</span>

<span class=rvts15>192.168.19.136 slave1</span>

<span class=rvts15>192.168.19.137 slave2</span>

<span class=rvts15>
</span>

<span class=rvts15>3&#12289;&#20813;&#23494;&#30331;&#24405;</span>

<span class=rvts15>ssh master</span>

<span class=rvts15>no</span>

<span class=rvts15>cd ~/.ssh</span>

<span class=rvts15>ssh-keygen -t rsa -P ''</span>

<span class=rvts15>cp id_rsa.pub authorized_keys</span>

<span class=rvts15>[root@slave1 .ssh]# cat ~/.ssh/authorized_keys | ssh root@master 'cat &gt;&gt; ~/.ssh/authorized_keys'</span>

<span class=rvts15>[root@slave2 .ssh]# cat ~/.ssh/authorized_keys | ssh root@master 'cat &gt;&gt; ~/.ssh/authorized_keys'</span>

<span class=rvts15>[root@master .ssh]# more authorized_keys </span>

<span class=rvts15>[root@master .ssh]# scp ~/.ssh/authorized_keys root@slave1:~/.ssh/</span>

<span class=rvts15>[root@master .ssh]# scp ~/.ssh/authorized_keys </span><span class=rvts17>root@slave2:~/.ssh/</span>

<span class=rvts15>ssh master</span>

<span class=rvts15>ssh slave1</span>

<span class=rvts15>ssh slave2</span>

<span class=rvts15>
</span>

<span class=rvts15>4&#12289;&#23433;&#35013;jdk</span>

<span class=rvts15>mkdir -p /opt/SoftWare/Java</span>

<span class=rvts15>mkdir -p /opt/SoftWare/Hadoop</span>

<span class=rvts15>yum install java-1.8.0-openjdk.x86_64 -y</span>

<span class=rvts15>vi /etc/profile</span>

<span class=rvts15>export JAVA_HOME=/usr/lib/jvm/jre-1.8.0-openjdk.x86_64/
</span>

<span class=rvts15>export PATH=$PATH:$JAVA_HOME/bin</span>

<span class=rvts15>source /etc/profile
</span>

<span class=rvts15>echo $JAVA_HOME</span>

<span class=rvts15>/usr/lib/jvm/jre-1.8.0-openjdk.x86_64/</span>

<span class=rvts15>
</span>

<span class=rvts15>5&#12289;&#23433;&#35013;hadoop</span>

<span class=rvts31>http://hadoop.apache.org/releases.html</span>

<span class=rvts15>[root@master ~]# cd /opt/SoftWare/Hadoop</span>

<span class=rvts15>[root@master Hadoop]# tar -zxvf hadoop-2.7.7.tar.gz</span>

<span class=rvts15>[root@master Hadoop]# cd hadoop-2.7.7</span>

<span class=rvts15>[root@master hadoop-2.7.7]# mkdir tmp</span>

<span class=rvts15>[root@master hadoop-2.7.7]# mkdir logs</span>

<span class=rvts15>[root@master hadoop-2.7.7]# mkdir -p hdfs/name</span>

<span class=rvts15>[root@master hadoop-2.7.7]# mkdir -p hdfs/data</span>

<span class=rvts42>[root@master hadoop-2.7.7]# vi etc/hadoop/hadoop-env.sh</span>

<span class=rvts15>export JAVA_HOME=/usr/lib/jvm/jre-1.8.0-openjdk-1.8.0.222.b10-0.el7_6.x86_64/</span>

<span class=rvts42>[root@master hadoop-2.7.7]# vi etc/hadoop/slaves </span>

<span class=rvts15>slave1</span>

<span class=rvts15>slave2</span>

<span class=rvts42>[root@master hadoop-2.7.7]# vi etc/hadoop/core-site.xml</span>

<span class=rvts15>&lt;!--&#22312;&lt;configuration&gt;&lt;/configuration&gt;&#20013;&#38388;&#28155;&#21152;&#19968;&#19979;&#20869;&#23481;--&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;fs.defaultFS&lt;/name&gt;&lt;!--&#23450;&#20041;Hadoop Master&#30340;URI&#21644;&#31471;&#21475;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;hdfs://master:9000&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;hadoop.tmp.dir&lt;/name&gt;&lt;!--hadoop&#30340;&#20020;&#26102;&#23384;&#20648;&#30446;&#24405;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;file:/opt/SoftWare/Hadoop/hadoop-2.7.7/tmp&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;io.file.buffer.size&lt;/name&gt;&lt;!--&#29992;&#20316;&#24207;&#21015;&#21270;&#25991;&#20214;&#22788;&#29702;&#26102;&#35835;&#20889;buffer&#30340;&#22823;&#23567;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;131702&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts42>[root@master hadoop-2.7.7]# vi etc/hadoop/hdfs-site.xml</span>

<span class=rvts15>&lt;!--&#22312;&lt;configuration&gt;&lt;/configuration&gt;&#20013;&#38388;&#28155;&#21152;&#19968;&#19979;&#20869;&#23481;--&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--namenode&#33410;&#28857;&#25968;&#25454;&#23384;&#20648;&#30446;&#24405;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.namenode.name.dir&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;file:/opt/SoftWare/Hadoop/hadoop-2.7.7/hdfs/name&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--datanode&#25968;&#25454;&#23384;&#20648;&#30446;&#24405;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.datanode.data.dir&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;file:/opt/SoftWare/Hadoop/hadoop-2.7.7/hdfs/data&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--&#25351;&#23450;DataNode&#23384;&#20648;block&#30340;&#21103;&#26412;&#25968;&#37327;,&#19981;&#22823;&#20110;DataNode&#30340;&#20010;&#25968;&#23601;&#34892;&#65292;&#40664;&#35748;&#20026;3--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.replication&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;2&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--&#25351;&#23450;master&#30340;http&#21327;&#35758;&#35775;&#38382;&#22320;&#22336;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.namenode.secondary.http-address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:50090&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--&#25351;&#23450;master&#30340;https&#21327;&#35758;&#35775;&#38382;&#22320;&#22336;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.namenode.secondary.https-address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;192.168.19.128:50091&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--&#24517;&#39035;&#35774;&#32622;&#20026;true&#65292;&#21542;&#21017;&#23601;&#19981;&#33021;&#36890;&#36807;web&#35775;&#38382;hdfs&#19978;&#30340;&#25991;&#20214;&#20449;&#24687;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;dfs.webhdfs.enabled&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;true&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts42>[root@master hadoop-2.7.7]# vi etc/hadoop/yarn-site.xml</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.nodemanager.aux-services&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;mapreduce_shuffle&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.nodemanager.aux-services.mapreduce.shuffle.class&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;org.apache.hadoop.mapred.ShuffleHandler&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.resourcemanager.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:8032&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.resourcemanager.scheduler.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:8030&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.resourcemanager.resource-tracker.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:8031&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.resourcemanager.admin.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:8033&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.resourcemanager.webapp.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:8088&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;yarn.nodemanager.resource.memory-mb&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;2048&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts42>[root@master hadoop-2.7.7]# cp etc/hadoop/mapred-site.xml.template etc/hadoop/mapred-site.xml</span>

<span class=rvts15>[root@master hadoop-2.7.7]# vi etc/hadoop/mapred-site.xml</span>

<span class=rvts15>&lt;property&gt;&lt;!--&#20351;&#29992;yarn&#36816;&#34892;mapreduce&#31243;&#24207;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;mapreduce.framework.name&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;yarn&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--MapReduce JobHistory Server&#22320;&#22336;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;mapreduce.jobhistory.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:10020&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts15>&lt;property&gt;&lt;!--MapReduce JobHistory Server Web&#30028;&#38754;&#22320;&#22336;--&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;name&gt;mapreduce.jobhistory.webapp.address&lt;/name&gt;</span>

<span class=rvts15>&nbsp; &nbsp;&lt;value&gt;master:19888&lt;/value&gt;</span>

<span class=rvts15>&lt;/property&gt;</span>

<span class=rvts42>[root@master hadoop-2.7.7]# scp -r /opt/SoftWare/Hadoop root@slave1:/opt/SoftWare/</span>

<span class=rvts42>[root@master hadoop-2.7.7]# scp -r /opt/SoftWare/Hadoop root@slave2:/opt/SoftWare/</span>

<span class=rvts15>vi /etc/profile</span>

<span class=rvts15>export HADOOP_HOME=/opt/SoftWare/Hadoop/hadoop-2.7.7</span>

<span class=rvts15>export HADOOP_LOG_DIR=$HADOOP_HOME/logs</span>

<span class=rvts15>export YARN_LOG_DIR=$HADOOP_LOG_DIR</span>

<span class=rvts15>export PATH=$HADOOP_HOME/bin:$HADOOP_HOME/sbin:$PATH</span>

<span class=rvts15>source /etc/profile</span>

<span class=rvts15>[root@master hadoop-2.7.7]# bin/hdfs namenode -format</span>

<span class=rvts15>#&#27880;&#24847;&#19978;&#38754;&#30340;&#31532;&#20108;&#34892;&#26368;&#21518;&#30340;successfully formatted</span>

<span class=rvts15>[root@master hadoop-2.7.7]# sbin/start-dfs.sh</span>

<span class=rvts15>[root@master hadoop-2.7.7]# sbin/start-yarn.sh</span>

<span class=rvts31>http://</span><span class=rvts15>192.168.19.128</span><span class=rvts31>:50070</span>

<span class=rvts31>http://</span><span class=rvts15>192.168.19.128</span><span class=rvts31>:8088</span><span class=rvts15>&nbsp;</span>

<span class=rvts15>
</span>

<span class=rvts15>
</span>

</body></html>