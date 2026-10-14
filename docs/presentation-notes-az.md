# Təqdimat üçün qısa qeydlər (AZ)

## 60–90 saniyəlik giriş

“Bu layihə Apex Enterprise Cybersecurity Lab adlanan geniş kibertəhlükəsizlik və infrastruktur laboratoriyasıdır. Burada məqsəd təkcə SOC monitorinqi deyil; təhlükəsiz web infrastrukturu, şəbəkə və endpoint müdafiəsi, identifikasiya və VPN girişləri, mərkəzləşdirilmiş loglama və təhlükəsizlik analitikası birlikdə öyrənilir.

Xarici veb hissədə React/Vite frontend, Node.js/Express backend və PostgreSQL istifadə olunur. Nginx reverse proxy rolunu oynayır, parollar bcrypt ilə hash-lənir, HTTPS və Fail2Ban əlavə qoruma yaradır. Intranet isə OpenVPN üzərindən giriş üçün nəzərdə tutulub.

Təhlükəsizlik hissəsinə SafeLine WAF, T-Pot honeypot, Bitdefender GravityZone XDR, Zammad ticketing və Splunk ilə əlaqəli WAF + IPS/IDS anomaly-analysis pipeline daxildir. Məqsəd hücum cəhdlərini müşahidə etmək, logları araşdırmaq və şübhəli hadisələri daha tez müəyyənləşdirməkdir.”

## Demo ardıcıllığı

1. **Arxitektura:** public web, WAF, web server, PostgreSQL, VPN/intranet və ayrı SIEM serverin rolunu göstər.
2. **External site:** test hesabı ilə login/register axınını göstər; real parol və tokenləri göstərmə.
3. **Database:** `password_hash` sahəsini göstər, real istifadəçi məlumatlarını və hash-ləri nümayiş etdirmə.
4. **Intranet:** VPN disconnected və connected vəziyyətində giriş sərhədini göstər.
5. **WAF:** qayda və bloklanmış test sorğusunu yalnız icazəli lab mühitində göstər.
6. **XDR:** GravityZone-da endpoint statusu və tətbiq edilmiş policy-ni göstər.
7. **Ticketing:** Zammad-da incident template, SLA və True/False Positive sahələrini izah et.
8. **SIEM/ML:** Splunk-da WAF və IPS/IDS mənbələrini, sonra ML nəticəsinin geri yazılmasını göstər.

## Dürüstlük qaydası

- Canlı yoxlamadığın inteqrasiyanı “tam avtomatikdir” kimi təqdim etmə.
- ML modelinin false positive-ləri azaltdığını demək üçün ölçülmüş müqayisə lazımdır.
- Öz gördüyün işlə komanda yoldaşının gördüyü işi ayır.
- Public IP, VPN profili, parol, token və şəxsi məlumatları nümayiş etdirmə.
