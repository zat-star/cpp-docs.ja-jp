---
title: "OLE DB プロバイダーの作成 | Microsoft Docs"
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
  - "OLE DB プロバイダー テンプレート, 作成 (プロバイダーを)"
  - "OLE DB プロバイダー, 作成"
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB プロバイダーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB プロバイダーを作成する方法として、ウィザードで ATL COM プロジェクトとプロバイダーを作成し、OLE DB テンプレートを使用してそのファイルを変更する方法をお勧めします。  プロバイダーをカスタマイズするときに、不要なプロパティをコメント アウトし、省略可能なインターフェイスを追加できます。  
  
 基本的な手順は次のとおりです。  
  
1.  ATL プロジェクト ウィザードを使用して基本のプロジェクト ファイルを作成し、ATL OLE DB プロバイダー ウィザードを使用してプロバイダーを作成します。\[クラスの追加\] の \[Visual C\+\+\] フォルダーの \[ATL OLE DB プロバイダー\] を選択します。  
  
2.  CMyProviderRS.h で `Execute` メソッドのコードを変更します。  例については、「[OLE DB プロバイダーへの文字列の読み込み](../Topic/Reading%20Strings%20into%20the%20OLE%20DB%20Provider.md)」を参照してください。  
  
3.  MyProviderDS.h、MyProviderSess.h、および MyProviderRS.h の各プロパティ マップを編集します。  ウィザードは、プロバイダーが実装する可能性のあるすべてのプロパティを含むプロパティ マップを作成します。  すべてのプロパティ マップを調べ、プロバイダーがサポートする必要のないプロパティを削除またはコメント アウトします。  
  
4.  MyProviderRS.h にある PROVIDER\_COLUMN\_MAP を更新します。  例については、「[OLE DB プロバイダーへの文字列の格納](../../data/oledb/storing-strings-in-the-ole-db-provider.md)」を参照してください。  
  
5.  プロバイダーをテストする準備ができたら、プロバイダー列挙でプロバイダーを検索することによってテストできます。  列挙でプロバイダーを検索するテスト コードの例については、[CATDB](http://msdn.microsoft.com/ja-jp/003d516b-2bf6-444e-8be5-4ebaa0b66046) サンプルと [DBVIEWER](http://msdn.microsoft.com/ja-jp/07620f99-c347-4d09-9ebc-2459e8049832) サンプル、または「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の例を参照してください。  
  
6.  必要に応じてインターフェイスを追加します。  例については、「[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)」を参照してください。  
  
    > [!NOTE]
    >  既定では、OLE DB レベル 0 に準拠したコードが生成されます。  アプリケーションが必ずレベル 0 に準拠するようにする場合には、ウィザードが生成したインターフェイスをコードから削除しないでください。  
  
## 参照  
 [CATDB](http://msdn.microsoft.com/ja-jp/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/ja-jp/07620f99-c347-4d09-9ebc-2459e8049832)