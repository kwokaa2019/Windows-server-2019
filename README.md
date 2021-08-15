Windows server 2019從評估板升級到完整版


要啟用分為兩步：

      1、將評估版升級為標準版

      2、使用啟用工具啟用

啟用過程：

1、(以管理員身份執行)執行->CMD->輸入“DISM /online /Get-CurrentEdition”，看你的當前版本
</code></pre><p><img src="https://i.ibb.co/VtF56p7/Virtual-Box-Server2019-13-08-2021-13-54-13.png" alt="Virtual-Box-Server2019-13-08-2021-13-49-00.png" title="                   Virtual-Box-Server2019-13-08-2021-13-49-00.png"></p></div>
如果Standard，把“ServerStandardEval”中的Eval這四個字母去掉，就是你的當前版本。

我以這Windows Server 2019 Datacenter版的例子，顯示如下，如果是其他版本，需要替换掉对应的key和Edition
</code></pre><p><img src="https://i.ibb.co/8YbVq5s/Virtual-Box-Server2019-13-08-2021-13-54-26.png" alt="Virtual-Box-Server2019-13-08-2021-13-49-00.png" title="                   Virtual-Box-Server2019-13-08-2021-13-49-00.png"></p></div>



2、然後輸入“DISM /online /Set-Edition:ServerDatacenter /ProductKey:XXXXX-XXXXX-XXXXX-XXXXX-XXXXX /AcceptEula”，

這裡的ServerDatacenter就是我查出來的EDITION ID（注意你實際查出來是什麼就填寫什麼），ProductKey:序號

</p><p>Windows Server 2019評估轉換為Windows Server 2019標準：：</p><pre><code>dism /online /set-edition:ServerStandard /productkey: N69G4-B89J2-4G8F4-WWYCC-J464C /accepteula
</code></pre><p>Windows Server 2019評估轉換為Windows Server 2019 Datacenter版本：</p><pre><code>dism /online /set-edition:ServerDatacenter /productkey:WMDGN-G9PQG-XVVXX-R3X43-63DFG /accepteula
</code></pre><p><img src="https://i.ibb.co/7bT9VSW/Virtual-Box-Server2019-13-08-2021-14-00-02.png" alt="         .png" title="                  .png"></p></div>



3、重啟操作完成
</code></pre><p><img src="https://i.ibb.co/2jp3Wy4/Virtual-Box-Server2019-13-08-2021-14-07-37.png" alt="         .png" title="                  .png"></p></div>


提示

如需要要詳細資訊，請參閱Micrsof 「將目前的評估版轉換為目前的零售版」參考文件

https://docs.microsoft.com/zh-tw/windows-server/get-started/supported-upgrade-paths#converting-a-current-evaluation-version-to-a-current-retail-version

