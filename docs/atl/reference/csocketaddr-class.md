---
title: "CSocketAddr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ee3f69874460d09e495a237985a98ace19134a01
ms.lasthandoff: 02/24/2017

---
# <a name="csocketaddr-class"></a>CSocketAddr クラス
このクラスは、ホスト アドレス、IPv4 と IPV6 の両方の形式をサポートするホスト名に変換するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CSocketAddr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](#csocketaddr)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](#findaddr)|指定されたホスト名をホストのアドレスに変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|ホスト アドレスを IPv4 ホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|IPv6 ホスト名をホストのアドレスに変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|特定の要素にポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|ポインターを返すには、このメソッドを呼び出して、 **addrinfo**  ボックスの一覧です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、IP のバージョンが Windows で使用するネットワーク アドレスを検索するための柔軟なアプローチ ソケット API 関数やライブラリのソケット ラッパーを提供します。  
  
 ネットワーク アドレスを検索するために使用するこのクラスのメンバーは、Win32 API 関数を使用して[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)します。  
  
 このクラスは、両方の IPv4 と Ipv6 ネットワーク アドレスをサポートします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsocket.h  
  
##  <a name="csocketaddr"></a>CSocketAddr::CSocketAddr  
 コンストラクターです。  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>コメント  
 新しい`CSocketAddr`オブジェクトし、ホストに関する応答情報を含むリンク リストを初期化します。  
  
##  <a name="findaddr"></a>CSocketAddr::FindAddr  
 指定されたホスト名をホストのアドレスに変換するには、このメソッドを呼び出します。  
  
```
int FindAddr(
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスをピリオドで区切られました。  
  
 *szPortOrServiceName*  
 ポート番号またはホスト上のサービスの名前。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせです。  
  
 *addr_family*  
 アドレス ファミリ (PF_INET) など。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
 *ai_proto*  
 (移植または IPPROTO_IPV6) などのプロトコルです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 成功するのかどうか、計算されるアドレスを使用して参照されているリンクされたリストに格納された`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 ホスト名のパラメーターは、IPv4 または IPv6 のいずれかの形式である可能性があります。 このメソッドは、Win32 API 関数を呼び出して[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="findinet4addr"></a>CSocketAddr::FindINET4Addr  
 ホスト アドレスを IPv4 ホスト名を変換するには、このメソッドを呼び出します。  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスをピリオドで区切られました。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせです。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 成功するのかどうか、計算されるアドレスを使用して参照されているリンクされたリストに格納された`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 API 関数を呼び出して[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="findinet6addr"></a>CSocketAddr::FindINET6Addr  
 IPv6 ホスト名をホストのアドレスに変換するには、このメソッドを呼び出します。  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスをピリオドで区切られました。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせです。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 成功するのかどうか、計算されるアドレスを使用して参照されているリンクされたリストに格納された`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 API 関数を呼び出して[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo  
 特定の要素にポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 特定の要素への参照、 [addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530)  ボックスの一覧です。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 **addrinfo**によって参照される構造`nIndex`ホストに関する応答情報を含むリンク リストにします。  
  
##  <a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList  
 ポインターを返すには、このメソッドを呼び出して、 **addrinfo**  ボックスの一覧です。  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>戻り値  
 1 つまたは複数のリンク リストへのポインター`addrinfo`ホストに関する応答情報を含む構造体。 詳細については、`addrinfo`構造体の"addrinfo"記事を参照してください、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/linkid=556)  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

