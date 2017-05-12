---
title: "Platform::COMException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::COMException クラス"
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::COMException クラス
アプリケーションの実行中に発生する COM エラーを表します。 COMException は、一連の定義済みの標準例外の基底クラスです。  
  
## 構文  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
## メンバー  
 COMException クラスは、Object クラスと IException、IPrintable、および IEquatable インターフェイスから継承されます。  
  
 COMException には次の種類のメンバーもあります。  
  
 **コンストラクター**  
  
|メンバー|説明|  
|----------|--------|  
|`COMException`|COMException クラスの新しいインスタンスを初期化します。|  
  
 **メソッド**  
  
 COMException クラスは、[Platform::Object クラス](../cppcx/platform-object-class.md) から Equals\(\)、Finalize\(\)、GetHashCode\(\)、GetType\(\)、MemberwiseClose\(\)、および ToString\(\) メソッドを継承します。  
  
 **プロパティ**  
  
 COMException クラスには、次のプロパティがあります。  
  
|メンバー|説明|  
|----------|--------|  
|[Exception::HResult プロパティ](../cppcx/exception-hresult-property.md)|例外に対応する HRESULT。|  
|[Exception::Message プロパティ](../cppcx/exception-message-property.md)|例外を説明するメッセージ。|  
  
## 派生例外  
 次の定義済みの例外は COMException から派生します。 これらは、その名前、コンストラクターの名前、および基になる HRESULT 値だけが COMException とは異なります。  
  
|名前|基になる HRESULT|説明|  
|--------|------------------|--------|  
|COMException|*ユーザー定義の hresult*|COM メソッドの呼び出しから認識されない HRESULT が返されるとスローされます。|  
|AccessDeniedException|E\_ACCESSDENIED|リソースや機能へのアクセスが拒否されるとスローされます。|  
|ChangedStateException|E\_CHANGED\_STATE|親コレクションが変更された後にコレクション反復子またはコレクション ビューのメソッドが呼び出されるとスローされ、メソッドの結果を無効にします。|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|COM クラスが登録されていないときにスローされます。|  
|DisconnectedException|RPC\_E\_DISCONNECTED|オブジェクトがクライアントから接続を切断されるとスローされます。|  
|FailureException|E\_FAIL|操作が失敗したときにスローされます。|  
|InvalidArgumentException|E\_INVALIDARG|メソッドに渡された引数のいずれかが無効な場合にスローされます。|  
|InvalidCastException|E\_NOINTERFACE|型が別の型にキャストできないときにスローされます。|  
|NotImplementedException|E\_NOTIMPL|インターフェイス メソッドがクラスに実装されていないときにスローされます。|  
|NullReferenceException|E\_POINTER|null オブジェクト参照を逆参照しようするとスローされます。|  
|OperationCanceledException|E\_ABORT|操作が中止されるとスローされます。|  
|OutOfBoundsException|E\_BOUNDS|操作が有効範囲外のデータにアクセスを試みるとスローされます。|  
|OutOfMemoryException|E\_OUTOFMEMORY|メモリが不足して操作を完了できないときにスローされます。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)