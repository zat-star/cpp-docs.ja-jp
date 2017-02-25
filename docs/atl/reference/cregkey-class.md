---
title: "CRegKey クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRegKey"
  - "ATL::CRegKey"
  - "ATL.CRegKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, レジストリ"
  - "CRegKey クラス"
  - "レジストリ, 削除 (キーを)"
  - "レジストリ, 削除 (値を)"
  - "レジストリ, 書き込み"
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CRegKey クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、システム レジストリ内のエントリを操作するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CRegKey  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRegKey::CRegKey](../Topic/CRegKey::CRegKey.md)|コンストラクターです。|  
|[CRegKey::~CRegKey](../Topic/CRegKey::~CRegKey.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRegKey::Attach](../Topic/CRegKey::Attach.md)|[m\_hKey](../Topic/CRegKey::m_hKey.md) メンバー ハンドルの値に `hKey` を設定して、HKEY を `CRegKey` オブジェクトに結び付けます。|  
|[CRegKey::Close](../Topic/CRegKey::Close.md)|[m\_hKey](../Topic/CRegKey::m_hKey.md) メンバー ハンドルを解放し、このメンバー ハンドルの値に NULL を設定します。|  
|[CRegKey::Create](../Topic/CRegKey::Create.md)|指定されたキーが `hKeyParent` のサブキーとして存在しない場合は、そのキーを作成します。|  
|[CRegKey::DeleteSubKey](../Topic/CRegKey::DeleteSubKey.md)|指定されたキーをレジストリから削除します。|  
|[CRegKey::DeleteValue](../Topic/CRegKey::DeleteValue.md)|[m\_hKey](../Topic/CRegKey::m_hKey.md) から値フィールドを削除します。|  
|[CRegKey::Detach](../Topic/CRegKey::Detach.md)|`CRegKey` オブジェクトから [m\_hKey](../Topic/CRegKey::m_hKey.md) メンバー ハンドルを切り離し、`m_hKey` の値に NULL を設定します。|  
|[CRegKey::EnumKey](../Topic/CRegKey::EnumKey.md)|開いているレジストリ キーのサブキーを列挙します。|  
|[CRegKey::Flush](../Topic/CRegKey::Flush.md)|開いているレジストリ キーのすべての属性をレジストリに書き込みます。|  
|[CRegKey::GetKeySecurity](../Topic/CRegKey::GetKeySecurity.md)|開いているレジストリ キーを保護しているセキュリティ記述子のコピーを取得します。|  
|[CRegKey::NotifyChangeKeyValue](../Topic/CRegKey::NotifyChangeKeyValue.md)|開いているレジストリ キーの属性や内容の変更について、呼び出し元に通知します。|  
|[CRegKey::Open](../Topic/CRegKey::Open.md)|指定されたキーを開き、[m\_hKey](../Topic/CRegKey::m_hKey.md) の値にこのキーのハンドルを設定します。|  
|[CRegKey::QueryBinaryValue](../Topic/CRegKey::QueryBinaryValue.md)|指定された値名のバイナリ データを取得します。|  
|[CRegKey::QueryDWORDValue](../Topic/CRegKey::QueryDWORDValue.md)|指定された値名の DWORD データを取得します。|  
|[CRegKey::QueryGUIDValue](../Topic/CRegKey::QueryGUIDValue.md)|指定された値名の GUID データを取得します。|  
|[CRegKey::QueryMultiStringValue](../Topic/CRegKey::QueryMultiStringValue.md)|指定された値名の複数文字列データを取得します。|  
|[CRegKey::QueryQWORDValue](../Topic/CRegKey::QueryQWORDValue.md)|指定された値名の QWORD データを取得します。|  
|[CRegKey::QueryStringValue](../Topic/CRegKey::QueryStringValue.md)|指定された値名の文字列データを取得します。|  
|[CRegKey::QueryValue](../Topic/CRegKey::QueryValue.md)|[m\_hKey](../Topic/CRegKey::m_hKey.md) の値フィールドのうち、指定された値フィールドのデータを取得します。  以前のバージョンのこのメソッドはサポートされず、**ATL\_DEPRECATED** のマークが付いています。|  
|[CRegKey::RecurseDeleteKey](../Topic/CRegKey::RecurseDeleteKey.md)|指定されたキーをレジストリから削除し、サブキーがあればそれも削除します。|  
|[CRegKey::SetBinaryValue](../Topic/CRegKey::SetBinaryValue.md)|レジストリ キーのバイナリ値を設定します。|  
|[CRegKey::SetDWORDValue](../Topic/CRegKey::SetDWORDValue.md)|レジストリ キーの DWORD 値を設定します。|  
|[CRegKey::SetGUIDValue](../Topic/CRegKey::SetGUIDValue.md)|レジストリ キーの GUID 値を設定します。|  
|[CRegKey::SetKeySecurity](../Topic/CRegKey::SetKeySecurity.md)|レジストリ キーのセキュリティを設定します。|  
|[CRegKey::SetKeyValue](../Topic/CRegKey::SetKeyValue.md)|指定されたキーの指定された値フィールドにデータを格納します。|  
|[CRegKey::SetMultiStringValue](../Topic/CRegKey::SetMultiStringValue.md)|レジストリ キーの複数文字列値を設定します。|  
|[CRegKey::SetQWORDValue](../Topic/CRegKey::SetQWORDValue.md)|レジストリ キーの QWORD 値を設定します。|  
|[CRegKey::SetStringValue](../Topic/CRegKey::SetStringValue.md)|レジストリ キーの文字列値を設定します。|  
|[CRegKey::SetValue](../Topic/CRegKey::SetValue.md)|[m\_hKey](../Topic/CRegKey::m_hKey.md) の指定された値フィールドにデータを格納します。  以前のバージョンのこのメソッドはサポートされず、**ATL\_DEPRECATED** のマークが付いています。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CRegKey::operator HKEY](../Topic/CRegKey::operator%20HKEY.md)|`CRegKey` オブジェクトを HKEY に変換します。|  
|[CRegKey::operator \=](../Topic/CRegKey::operator%20=.md)|代入演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CRegKey::m\_hKey](../Topic/CRegKey::m_hKey.md)|`CRegKey` オブジェクトに関連付けられたレジストリ キーのハンドルを保持します。|  
|[CRegKey::m\_pTM](../Topic/CRegKey::m_pTM.md)|`CAtlTransactionManager` のオブジェクトへのポインター。|  
  
## 解説  
 `CRegKey` には、システム レジストリのキーと値を作成および削除するメソッドを提供します。  レジストリにインストールされた一連のインストールされているハードウェアのソフトウェア バージョン番号、論理的に物理的な割り当て、および COM オブジェクトなどのシステム コンポーネントの定義が含まれます。  
  
 `CRegKey` は、特定のコンピューターにレジストリにプログラミング インターフェイスを提供します。  たとえば、特定のレジストリ キーを開くには、呼び出し `CRegKey::Open`。  データ値、呼び出し `CRegKey::QueryValue` または `CRegKey::SetValue`を変更する取得や、それぞれ。  キーを閉じるには、`CRegKey::Close`を呼び出します。  
  
 キーを閉じると、レジストリ データは、ハード ディスクにフラッシュ書き込まれます。  この処理には数秒かかることがあります。  アプリケーションがハード ディスクに明示的にレジストリ データを記述する [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 の関数を呼び出すことができます。  ただし、**RegFlushKey** は絶対に必要な場合に限り多くのシステム リソースを使用し、呼び出す必要があります。  
  
> [!IMPORTANT]
>  呼び出し元がレジストリの場所を指定できるようにするメソッドは信頼できないデータを読み取る可能性があります。  [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) を利用するメソッドは、この関数を明示的に終了する null である文字列を処理しないことを考慮に入れる必要があります。  両方の条件を呼び出し元のコードからのチェックする必要があります。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [DCOM のサンプル](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [Registry Overview](http://msdn.microsoft.com/library/windows/desktop/ms724871)   
 [Registry Functions](http://msdn.microsoft.com/library/windows/desktop/ms724875)   
 [Registry Value Types](http://msdn.microsoft.com/library/windows/desktop/ms724884)