---
title: "ラッパー クラス | Microsoft Docs"
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
  - "ActiveX コントロール [C++], ラッパー クラス"
  - "データ バインディング [C++], ActiveX コントロール"
  - "ラッパー クラス [C++], ActiveX コントロール"
ms.assetid: ebbc17b9-cc1b-4c29-afa9-da7f9511876e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ラッパー クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ プロジェクトに[コントロールを挿入する](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)場合、既定では、コントロールのラッパー クラスは含まれません。  コントロールのラッパー クラスを作成しておくと、[コントロールの動作を変更する](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)ことができます。  作成するラッパー クラスの数は、プログラムでどのようにコントロールを操作するかによって決まります。  
  
 ラッパー クラスは、コントロールのタイプ ライブラリ \(.tlb\) ファイルの各コクラスで利用できます。  コントロールのラッパー クラスは、"C" で始まるコントロール名にする必要があります。  
  
 ラッパー クラスの機能の詳細については、コントロールの基本テクノロジのオブジェクト モデルを参照してください。  
  
 [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) を使用する場合も、戻り値をコントロール クラスにキャストする必要があるため、ラッパー クラスが必要です。  たとえば、次のようになります。  
  
```  
CDBList* pDBList = 0;  
pDBList = static_cast<CDBList*>(GetDlgItem(IDC_DBLIST));  
```  
  
 作成された .idl ファイルを見ると、コントロールから公開されているプロパティ、メソッド、およびイベントがわかります。また、メソッドとアクセサー関数の宣言もわかります。  コントロールから詳細情報を取得するには、[OLE\/COM オブジェクト ビューアー](../Topic/Using%20the%20OLE-COM%20Object%20Viewer.md)を使用します。  
  
## 参照  
 [ActiveX コントロールを使用する](../Topic/Using%20ActiveX%20Controls.md)   
 [コントロールの実行時の動作を変更する](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)