---
title: "Symbol Name Restrictions | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.restrictions.name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
  - "restrictions, symbol names"
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Symbol Name Restrictions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

シンボル名に関する制限は、次のとおりです。  
  
-   すべての[シンボル](../mfc/symbols-resource-identifiers.md)は、アプリケーションのスコープ内で一意である必要があります。  そうすることで、ヘッダー ファイルでのシンボル定義の競合を避けることができます。  
  
-   シンボル名で有効な文字は、A ～ Z、a ～ z、0 ～ 9、およびアンダー スコア \(\_\) です。  
  
-   シンボル名を数字で始めることはできず、247 文字までに制限されます。  
  
-   シンボル名にスペースを使用することはできません。  
  
-   シンボル名で大文字と小文字は区別されませんが、最初のシンボル定義での大文字と小文字の区別は維持されます。  シンボルを定義するヘッダー ファイルは、リソース ファイルで定義されているリソースを参照するために、リソース コンパイラ\/エディターと C\+\+ プログラムの両方で使用されます。  大文字か小文字かだけが異なる 2 つのシンボル名の場合、C\+\+ プログラムは 2 つの個別のシンボルと見なしますが、リソース コンパイラ\/エディターはどちらの名前も 1 つのシンボルを指していると見なします。  
  
    > [!NOTE]
    >  以下に概要が示されている標準シンボル名スキーム \(ID\*\_\[キーワード\]\) に従わず、シンボル名がリソース スクリプト コンパイラで使用されているキーワードと同じである場合、リソース スクリプト ファイルをビルドしようとすると、ランダムであるように見えるエラーが発生し、診断が困難になります。  これを回避するには、標準名前付けスキームに従います。  
  
 シンボル名には説明的なプレフィックスがあり、対象となるリソースやオブジェクトの種類を示します。  これらの説明的なプレフィックスは、テキストを組み合わせた ID で始まります。  Microsoft Foundation Class \(MFC\) ライブラリでは、以下の表に示されているシンボルの名前付け規則が使用されています。  
  
|カテゴリ|プレフィックス|使用|  
|----------|-------------|--------|  
|リソース|IDR\_ IDD\_ IDC\_ IDI\_ IDB\_|アクセラレータまたはメニュー \(および関連付けられているかカスタムのリソース\) ダイアログ ボックス カーソル アイコン ビットマップ|  
|メニュー項目|ID\_|メニュー項目|  
|コマンド|ID\_|コマンド|  
|コントロールと子ウィンドウ|IDC\_|コントロール|  
|文字列|IDS\_|文字列テーブル内の文字列|  
|MFC|AFX\_|定義済みの MFC シンボル用に予約されています|  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 必要条件  
 Win32  
  
## 参照  
 [Changing a Symbol or Symbol Name \(ID\)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Symbol Value Restrictions](../Topic/Symbol%20Value%20Restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)