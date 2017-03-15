---
title: "FtmBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FtmBase クラス"
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フリー スレッド マーシャラー オブジェクトを表します。  
  
## 構文  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags< WinRtClassicComMix >,   
   Microsoft::WRL::CloakedIid< IMarshal > >;  
```  
  
## 解説  
 詳細については、MSDN ライブラリの「COM 「IMarshal」を」COM インターフェイス ポインターのサブトピックを参照して」トピックを参照します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[FtmBase::FtmBase コンストラクター](../windows/ftmbase-ftmbase-constructor.md)|FtmBase クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[FtmBase::CreateGlobalInterfaceTable メソッド](../windows/ftmbase-createglobalinterfacetable-method.md)|グローバル インターフェイス テーブル \(GIT\) を作成します。|  
|[FtmBase::DisconnectObject メソッド](../windows/ftmbase-disconnectobject-method.md)|強制的にオブジェクトに対する外部接続を解放します。  オブジェクトのサーバーがシャットダウンする前にこのオブジェクトのメソッドの実装を呼び出します。|  
|[FtmBase::GetMarshalSizeMax メソッド](../windows/ftmbase-getmarshalsizemax-method.md)|指定されたオブジェクトの指定されたインターフェイス ポインターをマーシャリングするために必要なバイト数の上限を取得します。|  
|[FtmBase::GetUnmarshalClass メソッド](../windows/ftmbase-getunmarshalclass-method.md)|対応するプロキシのコードを含む DLL を検索するときに COM を使用する CLSID を取得します。  COM は、プロキシの初期化されていないインスタンスを作成するには、この DLL を読み込みます。|  
|[FtmBase::MarshalInterface メソッド](../Topic/FtmBase::MarshalInterface%20Method.md)|ストリームにクライアント プロセスのプロキシ オブジェクトを初期化するために必要なデータを書き込みます。|  
|[FtmBase::ReleaseMarshalData メソッド](../Topic/FtmBase::ReleaseMarshalData%20Method.md)|マーシャリングされたデータ パケットを破棄します。|  
|[FtmBase::UnmarshalInterface メソッド](../windows/ftmbase-unmarshalinterface-method.md)|新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイス ポインターを返します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[FtmBase::marshaller\_ データ メンバー](../windows/ftmbase-marshaller-data-member.md)|フリー スレッド マーシャラーへの参照が保持されます。|  
  
## 継承階層  
 `FtmBase`  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)