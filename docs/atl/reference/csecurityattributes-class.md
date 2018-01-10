---
title: "CSecurityAttributes クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs: C++
helpviewer_keywords: CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 918f90c9f04736eb2328d989e21b7b9997edab86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes クラス
このクラスは、セキュリティ属性の構造体の thin ラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Csecurityattributes::set](#set)|属性を設定するには、このメソッドを呼び出して、`CSecurityAttributes`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 **SECURITY_ATTRIBUTES**構造に含まれる、[セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379561)オブジェクトの作成に使用して、この構造体を指定することによって取得されたハンドルが継承可能かどうかを指定します。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>CSecurityAttributes::CSecurityAttributes  
 コンストラクターです。  
  
```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSecurityDescriptor`  
 セキュリティ記述子への参照。  
  
 `bInheritsHandle`  
 新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。  
  
##  <a name="set"></a>Csecurityattributes::set  
 属性を設定するには、このメソッドを呼び出して、`CSecurityAttributes`オブジェクト。  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSecurityDescriptor`  
 セキュリティ記述子への参照。  
  
 `bInheritHandle`  
 新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コンス トラクターによって初期化に使用、`CSecurityAttributes`オブジェクト。  
  
## <a name="see-also"></a>参照  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
