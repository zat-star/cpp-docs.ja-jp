---
title: "CMyProviderCommand (MyProviderRS.H) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67a394ce3c3b05e3f5eea49cbd3a234a0dd89df2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)
`CMyProviderCommand`クラスは、プロバイダー コマンド オブジェクトの実装です。 実装を提供、 `IAccessor`、 `ICommandText`、および**ICommandProperties**インターフェイスです。 `IAccessor`インターフェイスは、行セット内の 1 つと同じです。 コマンド オブジェクトでは、アクセサーを使用して、バインド パラメーターを指定します。 行セット オブジェクトでは、出力列のバインドを指定するのに、それらを使用します。 `ICommandText`インターフェイスは、テキスト コマンドを指定する便利な方法です。 この例では、`ICommandText`インターフェイスの後でカスタム コードを追加する場合以外もオーバーライドの場合は、`ICommand::Execute`メソッドです。 **ICommandProperties**インターフェイスは、すべてのコマンドや行セット オブジェクトのプロパティを処理します。  
  
```  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
 `IAccessor`インターフェイス コマンドと行セットで使用されるすべてのバインドを管理します。 コンシューマーは**iaccessor::createaccessor**の配列で**DBBINDING**構造体。 各**DBBINDING**構造には列のバインドの型と長さ) などの処理方法に関する情報が含まれています。 プロバイダーは、構造体を受け取り、データの転送方法と、すべての変換が必要かどうかを判断します。 `IAccessor`インターフェイスは、コマンドのパラメーターを処理するコマンド オブジェクトで使用します。  
  
 コマンド オブジェクトは、の実装も用意されています。`IColumnsInfo`です。 OLE DB が必要です、`IColumnsInfo`インターフェイスです。 インターフェイスは、コマンドからパラメーターに関する情報を取得するコンシューマーを使用します。 行セット オブジェクトを使用して、`IColumnsInfo`インターフェイスをプロバイダーに、出力列に関する情報を返します。  
  
 プロバイダーと呼ばれるインターフェイスも含まれています。`IObjectWithSite`です。 `IObjectWithSite`インターフェイスは、ATL 2.0 が実装されていたでき、その子にそれ自体に関する情報を渡すインプリメンタです。 コマンド オブジェクトを使用して、`IObjectWithSite`いずれかを通知する情報が行セット オブジェクトが作成したかの概要を生成します。  
  
## <a name="see-also"></a>参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)