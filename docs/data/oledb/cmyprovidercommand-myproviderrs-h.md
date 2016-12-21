---
title: "CMyProviderCommand (MyProviderRS.H) | Microsoft Docs"
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
  - "cmyprovidercommand"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderCommand クラス MyProviderRS.H"
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderCommand (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMyProviderCommand` クラスは、プロバイダー コマンド オブジェクトのための実装です。  これは、`IAccessor`、`ICommandText`、および **ICommandProperties** の各インターフェイスの実装を提供します。  `IAccessor` は、行セットで使用されるものと同じインターフェイスです。  コマンド オブジェクトは、アクセサーを使用してパラメーター間の連結を指定します。  行セット オブジェクトは、出力列の連結を指定するために、これらの連結を使用します。  `ICommandText` インターフェイスを使用すると、コマンドをテキストとして指定できるため便利です。  この例では、`ICommandText` インターフェイスは、後でカスタム コードを追加するときに使用します。また、`ICommand::Execute` メソッドもオーバーライドします。  **ICommandProperties** インターフェイスは、コマンド オブジェクトと行セット オブジェクトで使用されるすべてのプロパティを処理します。  
  
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
  
 コマンドと行セットで使用される連結はすべて、`IAccessor` インターフェイスで操作します。  コンシューマーは、DBBINDING 構造体の配列を引数として IAccessor::CreateAccessor を呼び出します。  各 **DBBINDING** 構造体には、列バインディングの処理方法 \(型や長さなど\) を指示する情報が含まれています。  プロバイダーは構造体を受け取り、データをどのように転送しらたよいか、変換の必要はないかを指定します。  `IAccessor` インターフェイスは、コマンドのパラメーターを処理するためにコマンド オブジェクトで使用されます。  
  
 コマンド オブジェクトは、`IColumnsInfo` の実装も提供します。  OLE DB には、`IColumnsInfo` インターフェイスも必要です。  コンシューマーは、インターフェイスを使用して、コマンドからのパラメーターに関する情報を取得できます。  行セット オブジェクトは、`IColumnsInfo` インターフェイスを使用して、出力列に関する情報をプロバイダーに返します。  
  
 プロバイダーには、`IObjectWithSite` インターフェイスも含まれます。  `IObjectWithSite` インターフェイスは ATL 2.0 より実装されました。このインターフェイスを使用すると、実装側は自身に関する情報を子に渡すことができます。  コマンド オブジェクトは、`IObjectWithSite` 情報を使用して、生成された行セット オブジェクトに、その行セット オブジェクトの作成元を知らせます。  
  
## 参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)