Windows server 2016/2019从评估板升级到完整版
要啟用分為兩步：

      1、將評估版升級為標準版

      2、使用啟用工具啟用

啟用過程：

1、(以管理員身份執行)執行->CMD->輸入“DISM /online /Get-CurrentEdition”，看你的當前版本

如果是評估版，例如Standard，把“ServerStandardEval”中的Eval這四個字母去掉，就是你的當前版本。
</code></pre><p><img src="                .png" alt="                  .png" title="                        .png"></p></div>





2、然後輸入“DISM /online /Set-Edition:ServerStandard /ProductKey:XXXXX-XXXXX-XXXXX-XXXXX-XXXXX /AcceptEula”，




</p><p>Windows Server 2019評估轉換為Windows Server 2019標準：：</p><pre><code>dism /online /set-edition:ServerStandard /productkey: N69G4-B89J2-4G8F4-WWYCC-J464C /accepteula
</code></pre><p>Windows Server 2019評估轉換為Windows Server 2019 Datacenter版本：</p><pre><code>dism /online /set-edition:ServerDatacenter /productkey:WMDGN-G9PQG-XVVXX-R3X43-63DFG /accepteula
</code></pre><p><img src="                      .png" alt="         .png" title="                  .png"></p></div>
        </div>


這裡的ServerStandard就是我查出來的EDITION ID（注意你實際查出來是什麼就填寫什麼），ProductKey後面的序列號見附錄。

3、重啟等待一會即可。 

操作完成，最後按照命令重啟計算機，就可以了。 
