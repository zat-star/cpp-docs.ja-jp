---
title: "OLE DB プログラミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f130c5d17a1a753d97cded0ab987305cc6a75c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-programming"></a>OLE DB プログラミング
Microsoft OLE DB は、レガシ テクノロジです。新しいアプリケーションのリンクの SQL サーバーの必要なデータ アクセス API です。 その他のすべての新しいアプリケーションでは、ODBC を使用する必要があります。 SQL Server の現在の OLE DB プロバイダーは、SQLNCLI11 です。DLL です。 プロバイダーは SQL Server 2016 でまだ出荷されています。 このドキュメントは、OLE DB を既に使用している既存のアプリケーションを維持している開発者向けです。
  
 OLE DB テンプレートは、一般的に使用される多数の OLE DB インターフェイスを実装するクラスを提供して、高性能な OLE DB データベース テクノロジを使いやすくする C++ テンプレートです。 このテンプレート ライブラリはコンシューマー テンプレートとプロバイダー テンプレートに分かれています。  
  
 Visual C++ には OLE DB のスターター アプリケーションを作成するためのウィザードのサポートもあります。  
  
 また、属性を使って OLE DB コンシューマー テンプレートを実装することもできます。  
  
|詳細情報|参照トピック|  
|-------------------------|---------|  
|OLE DB コンシューマー テンプレートの使用方法 (概念説明のトピック)|[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)|  
|OLE DB プロバイダー テンプレートの使用方法 (概念説明のトピック)|[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)|  
|OLE DB テンプレート クラスおよびマクロ|[OLE DB テンプレート リファレンス](../../data/oledb/ole-db-templates.md)(Visual C)|  
|OLE DB コンシューマー属性|[OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)|  
|OLE DB インターフェイス|[OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/en-us/library/ms713643.aspx)(、Windows SDK の)|  
|OLE DB テンプレート サンプル|[OLE DB テンプレート サンプル](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)| 
|データ アクセス プログラミングの概要 (Visual C++)|[データ アクセス プログラミング](../../data/data-access-programming-mfc-atl.md)|  
|ODBC の概念説明のトピック|[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)|  

  
## <a name="see-also"></a>関連項目  
 [データ アクセス](../data-access-in-cpp.md)