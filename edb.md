```jsp
    $(document).ready(function(){
    	//20200113 KEDI 기능개선요청 메뉴 권한별 Array 선언(추후 DB에서 가져옴)
    	//개발업체 KLIC + 선운소프트
    	var developerArr = ['klic_bjkim','klic_gwkim','klic_hckim','klic_ikhwang','klic_islee'
    					    ,'klic_jcwang','klic_jjkim','klic_jsjang','klic_khlee','klic_mwkim'
    						,'klic_smlee','klic_ssjeong','klic_wmpark','klic_wschoi','klic_yhjeon'
    						,'klic_yhsong','klic_ywryu'];
    	//기능 담당자
    	var operArr = ['kedi_codake','kedi_coffee8310','kedi_hjleeag','kedi_imim1124'
    	               ,'kedi_jiyeub','kedi_kang','kedi_ksh5011','kedi_lugz','kedi_minhee','kedi_ml1018k'
    	               ,'kedi_p9281','kedi_rmaqkd23','kedi_sunw','kedi_ugee','kedi_ujinjang','kedi_uykgnod'
    	               ,'kedi_yousho','kedi_ysh8873','kedi_bts7623','kedi_hario','kedi_eh9494'];
    	//메뉴 관리자
    	var menuAdmArr = ['kedi_bts7623','kedi_hario','kedi_eh9494'];

    	//해당 권한 부여
    	var devFlag = 'N';
    	var operFlag = 'N';
    	var menuAdmFlag = 'N';
    	if(developerArr.indexOf("<c:out value="${userInfo.userId}" />") >= 0){ devFlag = 'Y'; }
    	if(operArr.indexOf("<c:out value="${userInfo.userId}" />") >= 0){ operFlag = 'Y'; }
    	if(menuAdmArr.indexOf("<c:out value="${userInfo.userId}" />") >= 0){ menuAdmFlag = 'Y';	}

       	//권한에 따른 버튼 보여주기
    	function fn_stusBtnSet(stus){
			if(devFlag == 'Y' || menuAdmFlag == 'Y'){//개발자, 메뉴 관리자
				switch(stus){
				case '접수반려':
					$('#returnCancelBtn').css('display', 'inline-block');//반려취소
					break;
				case '접수':
					$('#progressBtn').css('display', 'inline-block');//진행
					$('#returnBtn').css('display', 'inline-block');//반려
					break;
				case '접수진행':
					$('#dtApplcBtn').css('display', 'inline-block');//DT적용
					$('#operApplcBtn').css('display', 'inline-block');//운영적용
					break;
				case 'DT반려':
					$('#dtApplcBtn').css('display', 'inline-block');//DT적용
					break;
				case 'DT확인':
				case '운영반려':
					$('#operApplcBtn').css('display', 'inline-block');//운영적용
					break;
				}
			}

			if(operFlag == 'Y' || menuAdmFlag == 'Y'){//기능 담당자, 메뉴 관리자
				switch(stus){
				case 'DT적용':
					$('#cnfirmDtBtn').css('display', 'inline-block');//DT확인
					$('#rqesterReturnBtn').css('display', 'inline-block');//DT반려
					break;
				case '운영적용':
					$('#managtComptBtn').css('display', 'inline-block');//조치완료
					$('#rqesterReturnOperBtn').css('display', 'inline-block');//운영반려
					break;
				case '접수반려':
					$('#managtComptBtn').css('display', 'inline-block');//조치완료
					break;
				case '요청':
				case '접수':
					$('#modifyBtn').css('display', 'inline-block');//수정
					break;
				}
			}

			if(menuAdmFlag == 'Y'){//메뉴 관리자일 경우
				if(stus == '요청'){
					$('#receiptBtn').css('display', 'inline-block');//접수
				}else if(stus == '접수' && !"<c:out value="${reqInfo.dvlprId}" />"){
					$('#receiptCancelBtn').css('display', 'inline-block');//접수취소
				}
				$('#deleteBtn').css('display', 'inline-block');//삭제
			}
    	}
    	fn_stusBtnSet("<c:out value="${reqInfo.reqStusCodeNm}" />");
```

---

```jsp
<div class="btn_area fr">
    <c:if test="${userInfo.authorCode == 'AD'}">
        <a href="#" title="저장" id="saveBtn" onclick="javascript:fn_save()" style="display:none;" class="btn_Ty09 Sav">저장</a>
        <a href="#" title="취소" id="cancelBtn" onclick="javascript:fn_cancel()" style="display:none;" class="btn_Ty09 Can">취소</a>
        <a href="#" title="접수" id="receiptBtn" onclick="javascript:fn_stusChg('receipt')" style="display:none;" class="btn_Ty09 App">접수</a>
        <a href="#" title="접수취소" id="receiptCancelBtn" onclick="javascript:fn_stusChg('receiptCancel')" style="display:none;" class="btn_Ty09 App">접수취소</a>
        <a href="#" title="반려취소" id="returnCancelBtn" onclick="javascript:fn_stusChg('returnCancel')" style="display:none;" class="btn_Ty09 App">반려취소</a>
        <a href="#" title="진행" id="progressBtn" onclick="javascript:fn_stusChg('progress')" style="display:none;" class="btn_Ty09 App">진행</a>
        <a href="#" title="반려" id="returnBtn" onclick="javascript:fn_stusChg('return')" style="display:none;" class="btn_Ty09 App">반려</a>
        <a href="#" title="DT적용" id="dtApplcBtn" onclick="javascript:fn_stusChg('dtApplc')" style="display:none;" class="btn_Ty09 App">DT적용</a>
        <a href="#" title="운영적용" id="operApplcBtn" onclick="javascript:fn_stusChg('operApplc')" style="display:none;" class="btn_Ty09 App">운영적용</a>
        <a href="#" title="DT적용" id="dtApplcBtn" onclick="javascript:fn_stusChg('dtApplc')" style="display:none;" class="btn_Ty09 App">DT적용</a>
        <a href="#" title="운영적용" id="operApplcBtn" onclick="javascript:fn_stusChg('operApplc')" style="display:none;" class="btn_Ty09 App">운영적용</a>
        <a href="#" title="DT확인" id="cnfirmDtBtn" onclick="javascript:fn_stusChg('cnfirmDt')" style="display:none;" class="btn_Ty09 App">DT확인</a>
        <a href="#" title="DT반려" id="rqesterReturnBtn" onclick="javascript:fn_stusChg('rqesterReturnDt')" style="display:none;" class="btn_Ty09 App">DT반려</a>
        <a href="#" title="조치완료" id="managtComptBtn" onclick="javascript:fn_stusChg('managtCompt')" style="display:none;" class="btn_Ty09 App">조치완료</a>
        <a href="#" title="운영반려" id="rqesterReturnOperBtn" onclick="javascript:fn_stusChg('rqesterReturnOper')" style="display:none;" class="btn_Ty09 App">운영반려</a>
        <a href="#" title="수정" id="modifyBtn" onclick="javascript:fn_modify()" style="display:none;" class="btn_Ty09 Mod">수정</a>
        <a href="#" title="삭제" id="deleteBtn" onclick="javascript:fn_delete()" style="display:none;" class="btn_Ty09 Del">삭제</a>
    </c:if>
    <a href="#goList" title="목록" onclick="javascript:fn_list()" class="btn_Ty09 Lis">목록</a>
</div>
```


1. display control이 아닌 자식 태그 추가하는 방식.
2. 태그를 하드코딩 말고 이쁘게 해보는 방법
3. 태그를 Array에 담아 꺼내쓰는 법
4. 관리자 권한 확인 되어야만 해당 BtnSet 함수 실행
