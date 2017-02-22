---
title: "MFC データベース ドキュメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], MFC"
  - "データベース [C++], MFC"
  - "MFC [C++], データベース アプリケーション"
  - "ODBC [C++], MFC"
ms.assetid: bb120282-cd0d-4bf4-a27c-93b3501fb3a0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC データベース ドキュメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DAO クラスと ODBC クラスの MFC ドキュメントの構成内容は次のとおりです。  
  
### MFC データベース ドキュメント  
  
|ドキュメントの内容|参照項目|  
|---------------|----------|  
|DAO および ODBC のクラス|『MFC リファレンス』の対応するクラス名|  
|DAO および ODBC のグローバル関数とグローバル マクロ|『MFC リファレンス』の対応する関数名またはマクロ名|  
|MFC ODBC クラスを用いるプログラミング|[ODBC と MFC](../data/odbc/odbc-and-mfc.md)|  
|DAO および ODBC のテクニカル ノート|[MFC テクニカル ノート](../mfc/technical-notes-by-category.md)|  
  
##  <a name="_core_mfc_documentation_and_dao_documentation"></a> MFC ドキュメントと DAO ドキュメント  
 MFC DAO クラス向けの MFC ドキュメントでは、オンライン ドキュメントに含まれる DAO SDK ドキュメントのトピックを参照しています。  MFC は DAO をカプセル化 \(ラップ\) しているため、MFC ドキュメントには以下の特徴があります。  
  
-   MFC を中心とし、さらに MFC と基になる DAO の実装との違いを明確にします。  
  
-   基礎となる DAO の詳細については、DAO SDK ヘルプ トピックを参照します。  このようなクロス リファレンスを示すには、必ず "DAO ヘルプ トピック *X*" と断ります。  
  
-   MFC と DAO の動作の違いを示します。  MFC はすべての DAO をラップするわけではありません。  たとえば、MFC には DAO のセキュリティ機能に対するオブジェクトは用意されていません。  
  
> [!NOTE]
>  DAO SDK のヘルプは、別のヘルプ ファイルに入っています。  このバージョンの Visual C\+\+ には、このドキュメントから DAO ヘルプにジャンプするためのハイパーテキスト リンクはありません。  
  
> [!NOTE]
>  DAO SDK ヘルプのトピックを参照するには、ある種の変換が必要になることがあります。  基本 DAO SDK ドキュメント内のサンプルは、C\+\+ ではなく Basic で書かれています。ただし、DAO SDK には、MFC を使用しない C\+\+ のサンプルがあります。  
  
##  <a name="_core_mfc_documentation_and_odbc_documentation"></a> MFC ドキュメントと ODBC ドキュメント  
 MFC ODBC クラスに関する MFC ドキュメントの構成は MFC DAO の場合と異なります。  MFC ODBC クラスは、ODBC API のラッパー クラスではなく、ODBC に依存する高度な抽象を提供します。  したがって、MFC ドキュメントと ODBC ドキュメントは、MFC ドキュメントと DAO ドキュメントほど密接には関連していません。  ODBC ドキュメントは Basic よりも C\+\+ にずっと近い C 言語を使用しています。  
  
## 参照  
 [MFC データベース クラス \(ODBC と DAO\)](../Topic/MFC%20Database%20Classes%20\(ODBC%20and%20DAO\).md)   
 [ODBC の基礎](../data/odbc/odbc-basics.md)