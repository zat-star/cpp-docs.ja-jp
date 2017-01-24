---
title: "ドット ディレクティブ | Microsoft Docs"
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
  - "ドット ディレクティブ (NMAKE の)"
  - "NMAKE プログラム, ドット ディレクティブ"
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ドット ディレクティブ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドット ディレクティブは、記述ブロックの外側で、行の先頭に指定します。  ドット ディレクティブはピリオド \( .\) で始まり、その後にコロン \(:\) が続きます。  空白とタブは使用できます。  ドット ディレクティブの名前には、大文字を使用します。  
  
|ディレクティブ|目的|  
|-------------|--------|  
|**.IGNORE :**|指定された位置からメイクファイルの最後まで、コマンドから返される 0 以外の終了コードを無視します。  既定では、コマンドで 0 以外の終了コードが返されると NMAKE は中断します。  エラー チェックを元に戻すには、**\!CMDSWITCHES** を使用します。  1 つのコマンドで終了コードを無視するには、ダッシュ \(–\) 修飾子を使用します。  ファイル全体で終了コードを無視するには、\/I を使用します。|  
|**.PRECIOUS :** *targets*|*targets* を更新するコマンドが中止された場合に、*targets* をディスクに保存します。ファイルを削除することによりコマンドで割り込みが処理される場合は無効です。  複数のターゲット名は、空白またはタブで区切ります。  既定では、**Ctrl** キーを押しながら **C** キーまたは **Break** キーを押すことでビルドが中断された場合、ターゲットは削除されます。  **.PRECIOUS** は、使用されるたびにメイクファイル全体に適用され、指示内容が累積されます。|  
|**.SILENT :**|指定された位置からメイクファイルの最後まで、実行されたコマンドを表示しません。  既定では、NMAKE が呼び出すコマンドが表示されます。  エコーを元に戻すには、**\!CMDSWITCHES** を使用します。  1 つのコマンドでエコーを中止するには、**@** 修飾子を使用します。  ファイル全体でエコーを中止するには、\/S を使用します。|  
|**.SUFFIXES :** `list`|推論規則で使用する拡張子を列挙します。拡張子 .exe .obj .asm .c .cpp .cxx .bas .cbl .for .pas .res .rc .f .f90 が含まれるようにあらかじめ定義されています。|  
  
 **.SUFFIXES** リストの順序を変更するか、または新しいリストを指定するには、リストの内容をクリアし、新しい設定を指定します。  リストの内容をクリアするには、次のようにコロンの後に拡張子がない状態にします。  
  
```  
.SUFFIXES :  
```  
  
 リストにサフィックスを追加するには、次のように指定します。  
  
```  
.SUFFIXES : suffixlist  
```  
  
 *suffixlist* は、追加するサフィックスのリストです。複数のサフィックスは、空白またはタブで区切ります。  **.SUFFIXES** の現在の設定を確認するには、\/P を使用して NMAKE を実行します。  
  
## 参照  
 [NMAKE リファレンス](../build/nmake-reference.md)