---
title: "リンカー入力としての .obj ファイル | Microsoft Docs"
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
  - ".obj ファイル (リンカー入力)"
  - "COFF ファイル"
  - "LINK ツール [C++], .obj ファイル"
  - "リンカー [C++], OBJ ファイル (入力)"
  - "OBJ ファイル (リンカー入力)"
  - "オブジェクト ファイル, リンカー出力"
  - "OMF オブジェクト ファイル"
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .obj ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンカー ツール \(LINK.EXE\) では、COFF \(Common Object File Format\) の .obj ファイルをリンクできます。  
  
## 解説  
 Microsoft では、Common Object File Format を定義するダウンロード可能なドキュメントを提供しています。  詳細について、ダウンロードのリビジョン 8.1 以降。[Microsoft Portable Executable and Common Object File Format の指定](http://go.microsoft.com/fwlink/?LinkId=93292)  
  
## Unicode のサポート  
 Visual Studio 2005 以降の Microsoft Visual C\+\+ コンパイラでは、ISO\/IEC の C 規格および C\+\+ 規格で定義されている Unicode 文字の識別子がサポートされます。  以前のバージョンのコンパイラでは、ASCII 文字の識別子しかサポートされていませんでした。  コンパイラおよびリンカーでは、Unicode の関数名、クラス名、およびスタティクス名をサポートするために、.obj ファイルの COFF 記号に Unicode UTF\-8 エンコーディングが使用されます。  UTF\-8 エンコーディングは、旧バージョンの Visual Studio で使用されていた ASCII エンコーディングと上位互換性があります。  
  
 コンパイラおよびリンカーの詳細については、「[コンパイラおよびリンカーでの Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)」を参照してください。  Unicode 規格の詳細について、構成を参照します [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123)。  
  
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [Unicode のサポート](../../text/support-for-unicode.md)   
 [コンパイラおよびリンカーでの Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Unicode 規格](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Common Object File Format の指定](http://go.microsoft.com/fwlink/?LinkId=93292)