---
title: "LINK コマンド ファイル | Microsoft Docs"
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
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ファイル [C++]"
  - "コマンド ファイル [C++], LINK"
  - "LINK ツール [C++]"
  - "LINK ツール [C++], コマンド ライン構文"
  - "構文, LINK コマンド ファイル"
  - "テキスト ファイル, 渡す (LINK に引数を)"
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LINK コマンド ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK へのコマンド ライン引数は、コマンド ファイルの形で渡すこともできます。  リンカーにコマンド ファイルを指定する場合は、次の構文を使います。  
  
```  
LINK @commandfile  
```  
  
 `commandfile` はテキスト ファイルの名前です。  アット マーク \(@\) とファイル名の間には、スペースやタブを挿入できません。  既定の拡張子はないため、必ず拡張子を付けた完全なファイル名を指定してください。  ワイルドカードは使用できません。  ファイル名には、絶対パスでも相対パスでも指定できます。  このファイルの検索には、環境変数で指定したパスは使用されません。  
  
 コマンド ファイルでは、コマンド ラインで指定する場合と同じように、引数をスペースかタブで区切ります。改行文字でも区切ることができます。  
  
 コマンド ファイルには、コマンド ラインの全体または一部を指定できます。  1 回の LINK コマンドで複数のコマンド ファイルを使うこともできます。  LINK はコマンド ファイルからの入力をコマンド ラインのその位置で指定されたものとして扱います。  コマンド ファイルは入れ子にできません。  [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md) オプションを指定しないと、コマンド ファイルの内容がエコーされます。  
  
## 使用例  
 次のコマンドは、DLL ファイルをビルドします。このコマンドは、オブジェクト ファイル名とライブラリのファイル名を別個のコマンド ファイルでリンカーに渡し、3 番目のコマンド ファイルで \/EXPORTS オプションを指定しています。  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)