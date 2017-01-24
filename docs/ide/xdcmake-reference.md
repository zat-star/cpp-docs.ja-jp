---
title: "XDCMake リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xdcmake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "xdcmake プログラム"
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XDCMake リファレンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

xdcmake.exe は、.xml ファイルに .xdc ファイルをコンパイルするプログラムです。  .xdc ファイルは各ソース・コード ファイルの Visual C\+\+ コンパイラでソース・コードが [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) してコンパイルする場合、ソース・コード ファイルが XML タグでマークされたドキュメント コメントを含むときに作成されます。  
  
### における xdcmake.exe を Visual Studio 開発環境で使用するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** フォルダーを開きます。  
  
3.  **\[XML Document Comments\]** のプロパティ ページをクリックします。  
  
> [!NOTE]
>  における xdcmake.exe のコマンド ライン オプションでは、xdcmake.exe を開発環境 \(プロパティ ページ\) で使用すると異なります。  開発環境での xdcmake.exe を使用する方法については、[\[XML ドキュメント ジェネレーター\] プロパティ ページ](../Topic/XML%20Document%20Generator%20Tool%20Property%20Pages.md)を参照してください。  
  
## 構文  
 xdcmake `input_filename options`  
  
## パラメーター  
 それぞれの文字について以下に説明します。  
  
 `input_filename`  
 xdcmake.exe の入力として使用する .xdc ファイルの名前。  一つ以上の .xdc ファイルを指定するか、または現在のディレクトリのすべての .xdc ファイルを使用するために \*.xdc を使用します。  
  
 `options`  
 次の個以上の:  
  
|オプション|説明|  
|-----------|--------|  
|\/。、\/help|xdcmake.exe のヘルプの表示。|  
|\/assembly:*ファイル名*|.xml ファイルに \<assembly\> のタグの値を指定できるようにします。  既定では、\<assembly\> のタグの値は、.xml ファイルの名前と同じです。|  
|\/nologo|著作権メッセージを表示しません。|  
|\/out:*ファイル名*|.xml ファイルの名前を指定できるようにします。  既定では、.xml ファイルの名前は、xdcmake.exe によって処理される最初の .xdc ファイルの名前です。|  
  
## 解説  
 Visual Studio でプロジェクトをビルドすると、xdcmake.exe を自動的に開始されます。  また、コマンド ラインでの xdcmake.exe を開始できます。  
  
 ソース・コード ファイルへのドキュメント コメントの追加の詳細については [ドキュメント コメントとして推奨されるタグ](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md) を参照してください。  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)