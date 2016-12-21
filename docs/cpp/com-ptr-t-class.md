---
title: "_com_ptr_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t クラス"
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_com_ptr_t` オブジェクトは COM インターフェイス ポインターをカプセル化し、"スマート" ポインターと呼ばれます。  このテンプレート クラスは、**IUnknown** メンバー関数 \(`QueryInterface`、`AddRef`、および **Release**\) の関数呼び出しによってリソースの割り当てと割り当て解除を管理します。  
  
 スマート ポインターは通常、**\_COM\_SMARTPTR\_TYPEDEF** マクロによって提供される typedef 定義で参照されます。  このマクロは、インターフェイス名と IID を受け取り、インターフェイスの名前と `Ptr` のサフィックスを指定して、`_com_ptr_t` の特殊化を宣言します。  次に例を示します。  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 このコードは、`_com_ptr_t` の特殊化である **IMyInterfacePtr** を宣言します。  
  
 一連の[関数テンプレート](../cpp/relational-function-templates.md)は、このテンプレート クラスのメンバーではなく、比較演算子の右側でスマート ポインターとの比較をサポートします。  
  
### 構築  
  
|||  
|-|-|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-com-ptr-t.md)|`_com_ptr_t` オブジェクトを構築します。|  
  
### 低水準操作  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|カプセル化されたインターフェイス ポインターで **IUnknown** の `AddRef` メンバー関数を呼び出します。|  
|[Attach](../Topic/_com_ptr_t::Attach.md)|このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|**CLSID** または **ProgID** を指定してオブジェクトの新しいインスタンスを作成します。|  
|[Detach](../cpp/com-ptr-t-detach.md)|カプセル化されたインターフェイス ポインターを抽出して返します。|  
|[GetActiveObject](../Topic/_com_ptr_t::GetActiveObject.md)|**CLSID** または **ProgID** の指定により、オブジェクトの既存のインスタンスにアタッチします。|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|カプセル化されたインターフェイス ポインターを返します。|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|カプセル化されたインターフェイス ポインターで **IUnknown** の `QueryInterface` メンバー関数を呼び出します。|  
|[Release](../cpp/com-ptr-t-release.md)|カプセル化されたインターフェイス ポインターで **IUnknown** の **Release** メンバー関数を呼び出します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../cpp/com-ptr-t-operator-equal.md)|既存の `_com_ptr_t` オブジェクトに新しい値を代入します。|  
|[operators \=\=、\!\=、\<、\>、\<\=、\>\=](../cpp/com-ptr-t-relational-operators.md)|スマート ポインター オブジェクトを、別のスマート ポインター、生のインターフェイス ポインター、または **NULL** と比較します。|  
|[抽出](../cpp/com-ptr-t-extractors.md)|カプセル化された COM インターフェイス ポインターを抽出します。|  
  
## END Microsoft 固有の仕様  
  
## 要件  
 **ヘッダー:** comip.h  
  
 **ライブラリ:** comsuppw.lib または comsuppwd.lib \(詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照\)  
  
## 参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)