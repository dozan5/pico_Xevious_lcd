# Raspberry Pi Pico版 Xeviousもどき  
ケンケン様作成の[MachiKania type M](http://www.ze.em-net.ne.jp/~kenken/machikania/typem.html)用に作成した「Xeviousもどき」を  
Raspberry Pi Picoへ移植しました。  
音声は単音PWM、3和音PWM、YAMAHAのFM音源（[YMF825Board](http://uda.la/fm/)) (要3.3V改造)。  
フレームレートはPIC版と同じく30fpsを達成。  
<ケンケン様HP>http://www.ze.em-net.ne.jp/~kenken/index.html  

※3和音PWMは　boochowp様　[楽しくやろう。](https://blog.boochow.com/)内の  
　[Raspberry Pi Picoでピコピコサウンドを出してみる](https://blog.boochow.com/article/pico-pwm-sound.html)  
　を参考にさせて頂きました。  
　尚　3和音PWMは仕組み上　音量は小さい為アンプが必要です 。  
 
40PIN液晶用  
![](Xevious1.jpg)  

Arduinoシールド用、　3和音シールド、　FM音源シールド　　
![](Xevious2.jpg)  

動作写真  
![](Xevious3.jpg)  
動画は[こちら](https://youtu.be/qzr7wMj9juU)で公開しています。  

## 回路図  
40PIN液晶用
![](Xevious_lcd_40pin.jpg)  
　　・JP1　picosoft製　Raspberry Pi Pico開発支援ボード  
　　・JP2　LCD032-2P/M032C9341B3等用  
　　・JP3　picosoft製　ゲームキーボード  
　　・JP4　ジャンパーピン　LCD_SEL　天地切替  
　　・JP5-0～JP5-7　ジャンパーピン　D0-D7/D8-D15　切替  
　　・JP6　ジャンパーピン　単音PWM SOUND ON/OFF  
　　・JP6-1,-2 (OPTOIN) 3和音PWM or FM音源  
　　・JP7-1,-2 (OPTION) スピーカー切替用  
    
Arduino液晶用,3和音用シールド,FM音源用シールド  
![](Xevious_lcd_Arduino.jpg)  
　　・JP1　picosoft製　Raspberry Pi Pico開発支援ボード  
　　・JP2　Arduino液晶用  
　　・JP3　picosoft製　ゲームキーボード  
　　・JP4　ジャンパーピン　LCD_SEL　天地切替  
　　・JP5　ジャンパーピン　単音PWM SOUND ON/OFF  
　　・JP6-1,-2 (OPTOIN) 3和音PWM or FM音源  
  
## 接続  
LCD 8Bitパラレル用の使用ポート  
　Pico　　　LCD  
　GPI 8　　　D0 or D8  
　GPI 9　　　D1 or D9  
　GPI10　　　D2 or D10  
　GPI11　　　D3 or D11  
　GPI12　　　D4 or D12  
　GPI13　　　D5 or D13  
　GPI14　　　D6 or D14  
　GPI15　　　D7 or D15  
　GPIO20　　RD  
　GPIO21　　WR  
　GPIO22　　RS  
　GPIO26　　CS  
　GPIO27　　RST  

## 公開プログラム  
uf2フォルダー  
　Normalフォルダー　・・・　単音PWM  
　PWMフォルダー　 ・・・・　3和音PWM  
　FMフォルダー　・・・・・　FM音源  

Arduinoシールド用　　　　　確認済みLCD  
　Xevious_lcd_9325_XXX.uf2　aitendo　M024C9325SLD (ILI9325)  
　Xevious_lcd_0154_XXX.uf2　aitendo　UL024C0154D8(S6D0154)  
　Xevious_lcd_8031_XXX.uf2　上記LCDで動作しない場合はお試しください。  

8Bit接続用　　　　　　　　　確認済みLCD  
　Xevious_lcd_9341_XXX.uf2　aitendo　M032C9341B3(ILI9341)    
　Xevious_lcd_1289_XXX.uf2　aitendo　LCD032-2P(SSD1289)  
　Xevious_lcd_8347_XXX.uf2　aitendo　M028C8347D8(HX8347D)  
　Xevious_lcd_9486_XXX.uf2　aitedno　M035C9486LB3(ILI9486L)  
　※LCDの解像度320x480の為　縦横を1.5倍に拡大しています。  
 
