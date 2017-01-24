---
title: "カスタム ビルド ステップまたはビルド イベントの出力の書式設定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビルド イベント [C++], 出力書式"
  - "ビルド ステップ [C++], 出力書式"
  - "ビルド [C++], ビルド イベント"
  - "ビルド [C++], カスタム ビルド ステップ"
  - "カスタム ビルド ステップ [C++], 出力書式"
  - "イベント [C++], ビルド"
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# カスタム ビルド ステップまたはビルド イベントの出力の書式設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム ビルド ステップまたはビルド イベントの出力が適切に書式設定されている場合は、ユーザーに次の利点があります。  
  
-   警告とエラーが**出力**ウィンドウにカウントされます。  
  
-   出力が**タスク一覧**ウィンドウに表示されます。  
  
-   **出力**ウィンドウで出力をクリックすると、適切なトピックが表示されます。  
  
-   F1 キー操作が、**タスク一覧**ウィンドウまたは**出力**ウィンドウで有効になります。  
  
 出力の書式は次のとおりです。  
  
 {*filename* \(*line\#* \[, *column\#*\]\) &#124; *toolname*} **:**  
  
 \[*any text*\] {**error** &#124; **warning**} *code\#\#\#\#***:** *localizable string*  
  
 \[ *any text* \]  
  
 指定項目:  
  
-   {*a* &#124; *b*}は *a* または *b*の選択です。  
  
-   \[`ccc`\] は、オプションの文字列またはパラメーターです。  
  
 たとえば、次のようになります。  
  
 C: \\*sourcefile.cpp* \(134\) : C2143 エラー: 構文エラー: 「見つからないという; 」の前に「}」  
  
 リンク: fatal error LNK1104: ファイル '*somelib.lib*"は開くことができません。  
  
## 参照  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)