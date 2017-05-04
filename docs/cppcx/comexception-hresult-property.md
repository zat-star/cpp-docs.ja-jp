---
title: "COMException::HResult プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMException::HResult プロパティ"
ms.assetid: 53762ab5-ce71-4397-b7b4-8175741c838f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# COMException::HResult プロパティ
例外に対応する HRESULT。  
  
## 構文  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## プロパティ値  
 エラーを指定する HRESULT 値。  
  
## 解説  
 HRESULT 値を解釈する方法の詳細については、「[COM エラー コードの構造](http://go.microsoft.com/fwlink/p/?LinkId=262045)」を参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## サブセクションの見出し  
  
## 参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)