---
title: "WeakRef クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef クラス"
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラシック COM ではなく、Windows ランタイムでのみ使用できる*弱い参照*を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。  
  
## 構文  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## コメント  
 WeakRef オブジェクトは、*強い参照*を保持します。これはオブジェクトと関連付けられ、有効な場合と無効な場合があります。 強い参照を取得するには、As\(\) や AsIID\(\) メソッドを呼び出します。 強い参照が有効な場合、関連付けられているオブジェクトにアクセスできます。 強い参照が無効な場合 \(`nullptr`\)、関連付けられているオブジェクトにアクセスできません。  
  
 WeakRef オブジェクトは通常、外部スレッドや外部アプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、ファイル オブジェクトへの参照から WeakRef オブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。  
  
 なお、Windows 10 SDK では [As](../windows/weakref-as-method.md)、[AsIID](../windows/weakref-asiid-method.md)、[CopyTo](../windows/weakref-copyto-method.md) の各メソッドの動作が変更されています。 以下のコードのように、以前は、これらのうちのいずれかのメソッドを呼び出した後、強い参照が正常に取得されたかどうかを判別するために `nullptr` の WeakRef を調べることができました。  
  
```cpp  
WeakRef wr; strongComptrRef.AsWeak(&wr); // Now suppose that the object strongComPtrRef points to no longer exists // and the following code tries to get a strong ref from the weak ref: ComPtr<ISomeInterface> strongRef; HRESULT hr = wr.As(&strongRef); // This check won't work with the Windows 10 SDK version of the library. // Use the HRESULT from previous As() call instead. if(wr == nullptr) { wprintf(L"Couldn’t get strong ref!"); }  
  
```  
  
 上記のコードは、Windows 10 SDK \(以降\) の使用時には機能しません。 代わりに、As や AsIID メソッドから返される HRESULT を確認するか、`nullptr` で渡されたポインターを確認します。  
  
```cpp  
if (hr != S_OK) { wprintf(L"Couldn't get strong ref!"); }  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[WeakRef::WeakRef コンストラクター](../windows/weakref-weakref-constructor.md)|WeakRef クラスの新しいインスタンスを初期化します。|  
|[WeakRef::~WeakRef デストラクター](../windows/weakref-tilde-weakref-destructor.md)|WeakRef クラスの現在のインスタンスの初期化を解除します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[WeakRef::As メソッド](../windows/weakref-as-method.md)|指定された ComPtr ポインター パラメーターを、指定されたインターフェイスを表すように設定します。|  
|[WeakRef::AsIID メソッド](../windows/weakref-asiid-method.md)|指定された ComPtr ポインター パラメーターを、指定されたインターフェイス ID を表すように設定します。|  
|[WeakRef::CopyTo メソッド](../windows/weakref-copyto-method.md)|インターフェイスへのポインターを、使用可能であれば指定されたポインター変数に割り当てます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[WeakRef::operator& 演算子](../Topic/WeakRef::operator&%20Operator.md)|現在の WeakRef オブジェクトを表す ComPtrRef オブジェクトを返します。|  
  
## 継承階層  
 `ComPtr`  
  
 `WeakRef`  
  
## 必要条件  
 **ヘッダー:**  client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)