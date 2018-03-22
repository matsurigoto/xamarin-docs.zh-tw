## <a name="firewall-configuration"></a>防火牆設定

為了讓提交到 Xamarin Test Cloud 進行測試，送出測試的電腦必須能夠與測試雲端伺服器通訊。 防火牆必須設定為允許從位於伺服器的網路流量**testcloud.xamarin.com**連接埠 80 和 443 上。 此端點管理 dns 和 IP 位址有所變更。 

在某些情況下，測試 （或執行測試的裝置） 必須受到防火牆的網頁伺服器與通訊。 在此案例中的防火牆必須設定成允許來自下列 IP 位址的流量：

* **195.249.159.238**
* **195.249.159.239**