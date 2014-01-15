MIST32 Instruction Format
==========

|Addr[Hex]|Addr[Dec]|Type|Instruction|Immediate|Mnemonic|Format1(Operand/Disp)|Format2(Imm)|Operation|Flag|AFE-Format1|AFE-Format2(Imm)|���s����|�g���b�v�ԍ�|��O�����̏���|���l|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|000|0|integer|add|�����g��|ADD|O2|I11|Rd = Rd + Rs||||||||
|001|1||sub|�����g��|SUB|O2|I11|Rd = Rd - Rs||||||||
|002|2||mul output Low 32bit|�����g��|MULL|O2|I11|Rd = (Rd * Rs) & 0xFFFFFFFF||||||||
|003|3||mul output High 32bit|�����g��|MULH|O2|I11|Rd = (Rd * Rs) >> 32||||||||
|004|4||unsigned div||UDIV|O2|I11|Rd = Rd / Rs|||||4|0���̎��i���ʂ�0�j||
|005|5||unsigned mod||UMOD|O2|I11|Rd = Rd % Rs|||||4|0���̎��i���ʂ�0�j||
|006|6||cmp|�����g��|CMP|O2|I11|FLAGR = flags(Rd, Rs)|||||||SUB���s�Ȃ��A���ʂ�j�����t���O�̂ݍX�V|
|007|7||signed div|�����g��|DIV|O2|I11|Rd = Rd / Rs|||||4|0���̎��i���ʂ�0�j||
|008|8||signed mod|�����g��|MOD|O2|I11|Rd = Rd % Rs|||||4|0���̎��i���ʂ�0�j||
|009|9||Sign Negative||NEG|O2||Rd = neg(Rs)|�t���O�𔭐����Ȃ�|||||||
|00A|10||unsigned mul output low 32bit||UMULL|O2|I11|||||||||
|00B|11||unsigned mul output high 32bit||UMULH|O2|I11|||||||||
|00D|13||increment(Cary Output)||IC|O2||Rd = cary_output(Rs + 1)||||||||
|00E|14||add cary output|�����g��|ADDC|O2|I11|Rd = cary_output(Rd + Rs)||||||||
|010|16||Inc||INC|O2||Rd = Rs + 1||||||||
|011|17||Dec||DEC|O2||Rd = Rs - 1||||||||
|013|19||signed Maximum||MAX|O2|I11|Rd = (Rd >= Rs)? Rd : Rs|�t���O�𔭐����Ȃ�|||||||
|014|20||signed Minimum||MIN|O2|I11|Rd = (Rd <= Rs)? Rd : Rs|�t���O�𔭐����Ȃ�|||||||
|015|21||unsigned Maximum||UMAX|O2|I11|Rd = (Rd >= Rs)? Rd : Rs|�t���O�𔭐����Ȃ�|||||||
|016|22||unsigned Minimum||UMIN|O2|I11|Rd = (Rd <= Rs)? Rd : Rs|�t���O�𔭐����Ȃ�|||||||
|01C|28||Sign Extension8->32||SEXT8|O2||Rd = Sign Extension8->32(Rs)|�t���O�𔭐����Ȃ�|||||||
|01D|29||Sign Extension16->32||SEXT16|O2||Rd = Sign Extension16->32(Rs)|�t���O�𔭐����Ȃ�|||||||
|040|64|Shift|logic shift left||SHL|O2|I11|Rd = Rd<<Rs|�Ō�ɒǂ��o���ꂽ�r�b�g��CF�ɐݒ�AOF�͏�Ƀ[���N���A||||1|64�ȏ�V�t�g�����ꍇ||
|041|65||logic shift right||SHR|O2|I11|Rd = Rd>>Rs|�Ō�ɒǂ��o���ꂽ�r�b�g��CF�ɐݒ�AOF�͏�Ƀ[���N���A||||1|64�ȏ�V�t�g�����ꍇ||
|045|69||alithmetic shift right||SAR|O2|I11|Rd = Rd>>>Rs|�Ō�ɒǂ��o���ꂽ�r�b�g��CF�ɐݒ�AOF�͏�Ƀ[���N���A||||1|64�ȏ�V�t�g�����ꍇ||
|048|72||rotate shift left||ROL|O2|I11|Rd = ROL(Rd, Rs)|�Ō�ɒǂ��o���ꂽ�r�b�g��CF�ɐݒ�(0bit�ڂɓ���r�b�g�Ɠ���)�AOF�͏�Ƀ[���N���A||||1|64�ȏ�V�t�g�����ꍇ||
|049|73||rotate shift right||ROR|O2|I11|Rd = ROR(Rd, Rs)|�Ō�ɒǂ��o���ꂽ�r�b�g��CF�ɐݒ�(31bit�ڂɓ���r�b�g�Ɠ���)�AOF�͏�Ƀ[���N���A||||1|64�ȏ�V�t�g�����ꍇ||
|060|96|Logic|and||AND|O2||Rd = Rd & Rs||||||||
|061|97||or||OR|O2||Rd = Rd | Rs||||||||
|062|98||xor||XOR|O2||Rd = Rd ^ Rs||||||||
|063|99||not||NOT|O2||Rd = ~Rs||||||||
|064|100||nand||NAND|O2||Rd = ~(Rd & Rs)||||||||
|065|101||nor||NOR|O2||Rd = ~(Rd | Rs)||||||||
|066|102||xnor||XNOR|O2||Rd = ~(Rd ^ Rs)||||||||
|067|103||test||TEST|O2||FLAGR = flags(Rd, Rs)||||||||
|06A|106||write 2Byte1/2�i����16�r�b�g�j||WL16|I16||Rd = Rd & 0xFFFF0000 | Rs|�t���O�𔭐����Ȃ�|||||||
|06B|107||write 2Byte2/2�i���16�r�b�g�j||WH16|I16||Rd = Rd & 0x0000FFFF | Rs << 16|�t���O�𔭐����Ȃ�|||||||
|06C|108||clear bit||CLRB||I11|Rd = clb(Rs)|�t���O�𔭐����Ȃ�|||||||
|06D|109||set bit||SETB||I11|Rd = stb(Rs)|�t���O�𔭐����Ȃ�|||||||
|06E|110||clear�@word||CLR|O1||Rd = 0x00000000|�t���O�𔭐����Ȃ�|||||||
|06F|111||set word||SET|O1||Rd = 0xFFFFFFFF|�t���O�𔭐����Ȃ�|||||||
|070|112||�r�b�g���o�[�X����||REVB|O2||Rd = rvbi(Rs)|�t���O�𔭐����Ȃ�|||||||
|071|113||�o�C�g���o�[�X����||REV8|O2||Rd = rvby(Rs)|�t���O�𔭐����Ȃ�|||||||
|072|114||Get Bit||GETB|O2|I11|Rd = (Rd >> Rs) & 0x00000001|�t���O�𔭐����Ȃ�|||||||
|073|115||Get Byte||GET8|O2|I11|Rd = (Rd >> Rs*8) & 0x000000FF|�t���O�𔭐����Ȃ�|||||||
|076|118||Signed Load Immediate(Low)||LIL||I16|Rd = SignExtension(Rs)|�t���O�𔭐����Ȃ�|||||||
|077|119||Signed Load Immediate(High)||LIH||I16|Rd = Rs<<16|�t���O�𔭐����Ȃ�|||||||
|07A|122||Unsigned Load Immediate||ULIL||I16|Rd = Rs||||||||
|080|128|Memory Access|load register or immediate||LD8|O2|I11|Rd = mask(MEMORY[Rs], 8)|�t���O�𔭐����Ȃ�|MA|MA||2|�������ی�ᔽ�̏ꍇ||
|081|129|||1bit���V�t�g|LD16|O2|I11|O2�̎� : Rd = mask(MEMORY[Rs], 16) I11�̎�Rd = mask(MEMORY[Rs>>1], 16)|�t���O�𔭐����Ȃ�|MA|MA||2|�������ی�ᔽ�̏ꍇ||
|082|130|||2bit���V�t�g|LD32|O2|I11|O2�̎� : Rd = mask(MEMORY[Rs], 16) I11�̎�Rd = mask(MEMORY[Rs>>2], 16)|�t���O�𔭐����Ȃ�|MA|MA||2|�������ی�ᔽ�̏ꍇ||
|083|131||store register or immediate||ST8|O2|I11|MEMORY[Rs] = mask(Rd, 8)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|084|132|||1bit���V�t�g|ST16|O2|I11|O2�̎� : MEMORY[Rs] = mask(Rd, 16) I11�̎� : MEMORY[Rs>>1] = mask(Rd, 16)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|085|133|||2bit���V�t�g|ST32|O2|I11|O2�̎� : MEMORY[Rs] = mask(Rd, 16) I11�̎� : MEMORY[Rs>>2] = mask(Rd, 16)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|088|136||push|�����g��|PUSH|O1|CI16|MEMORY[SPR] = Rd|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|089|137||Program Counter Push||PUSHPC|C||MEMORY[SPR] = PC + 8|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|090|144||pop||POP|O1||Rd = MEMORY[SPR]|�t���O�𔭐����Ȃ�||MA||2|�������ی�ᔽ�̏ꍇ||
|09A|154||with signed displacement||LDD8|O2||Rd = mask(MEMORY[Rs+displacement], 8)|�t���O�𔭐����Ȃ�|MA|||2|�������ی�ᔽ�̏ꍇ||
|09B|155||with signed displacement|1bit���V�t�g|LDD16|O2||Rd = mask(MEMORY[Rs+displacement], 16)|�t���O�𔭐����Ȃ�|MA|||2|�������ی�ᔽ�̏ꍇ||
|09C|156||with signed displacement|2bit���V�t�g|LDD32|O2||Rd = mask(MEMORY[Rs+displacement], 16)|�t���O�𔭐����Ȃ�|MA|||2|�������ی�ᔽ�̏ꍇ||
|09D|157||with signed displacement||STD8|O2||MEMORY[Rs] = mask(Rd+displacement, 8)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|09E|158||with signed displacement|1bit���V�t�g|STD16|O2||MEMORY[Rs] = mask(Rd+displacement, 16)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|09F|159||with signed displacement|2bit���V�t�g|STD32|O2||MEMORY[Rs] = mask(Rd+displacement, 16)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ||
|0A0|160|Branch|(PC relative addressing) register or imm Unsigned!|2bit���V�t�g|BUR|JO1|JI16|PC = PC + unsigned(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0A1|161||(PC relative addressing) register or imm Signed!|2bit���V�t�g|BR|JO1|JI16|PC = PC + signed(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0A2|162||(direct addressing)register or immediate|2bit���V�t�g|B|JO1|JI16|PC = unsigned(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0A3|163||(IRQ Ret)(direct addressing)register or immediate(CC Non Suport )|2bit���V�t�g|IB|C||PC = unsigned(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing ���荞�݃��[�`������̕��A�Ɏg�p(��������) CC��AL�����ΏۊO�B����ȊO�͖���`|
|0B0|176||(PC relative addressing) register or imm Unsigned!|2bit���V�t�g|BURN|JO1|JI16|PC = PC + unsigned(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0B1|177||(PC relative addressing) register or imm Signed!|2bit���V�t�g|BRN|JO1|JI16|PC = PC + signed(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0B2|178||(direct addressing)register or immediate|2bit���V�t�g|BN|JO1|JI16|PC = unsigned(Rd)|�t���O�𔭐����Ȃ�||||2|�������ی�ᔽ�̏ꍇ|Word Addressing|
|0C0|192|System Register Read|Stack Point Register Read||SRSPR|O1||Rd = SPR|�t���O�𔭐����Ȃ�|||||||
|0C1|193||PDTR Read||SRPDTR|O1||Rd = PDTR|�t���O�𔭐����Ȃ�|||||||
|0C2|194||CPU ID Read||SRPIDR|O1||Rd = CPUIDR|�t���O�𔭐����Ȃ�|||||||
|0C3|195||Core ID Read||SRCIDR|O1||Rd = COREIDR|�t���O�𔭐����Ȃ�|||||||
|0C4|196||Core Mode Read||SRMODER|O1||Rd = mask(SR1)|�t���O�𔭐����Ȃ�|||||||
|0C5|197||Interrupt Enable Information Read||SRIEIR|O1||Rd = (PSR & 0x00000004) >> 2|�t���O�𔭐����Ȃ�||||||1�ŋ���|
|0C8|200||TISR Read ||SRTISR|O1||Rd = TISR|�t���O�𔭐����Ȃ�|||�J�[�l�����[�h�̂ݎ��s�\|3|�����ᔽ||
|0C9|201||KPDTR||SRKPDTR|O1||Rd = KPDTR|�t���O�𔭐����Ȃ�|||�J�[�l�����[�h�̂ݎ��s�\|3|�����ᔽ||
|0CA|202||MMU Mode Read||SRMMUR|O1||Rd = mask(SR1)|�t���O�𔭐����Ȃ�||||||0=�A�h���X�ϊ��Ȃ�, 1=�\��, 2=1�i�ϊ�, 3=2�i�ϊ�|
|0CB|203||IOSR Read||SRIOSR|O1||Rd = IOSR|�t���O�𔭐����Ȃ�|||||||
|0CC|204||Task ID(TID) Read||SRTIDR|O1||Rd = TIDR|�t���O�𔭐����Ȃ�|||||||
|0CD|205||PPSR Read||SRPPSR|O1|||�t���O�𔭐����Ȃ�|||||||
|0CE|206||PPCR Read||SRPPCR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D0|208||PPDTR Read||SRPPDTR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D1|209||PTIDR Read||SRPTIDR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D3|211||PSR Read||SRPSR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D4|212||FRCR -> {FRCHR, FRCLW}||SRFRCR|C|||�t���O�𔭐����Ȃ�|||||||
|0D5|213||FRCLR Read||SRFRCLR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D6|214||FRCHR Read||SRFRCHR|O1|||�t���O�𔭐����Ȃ�|||||||
|0D7|215||PFLAGR Read||SRPFLAGR|O1||Rd = SRPFLAGR|�t���O�𔭐����Ȃ�|||||||
|0E0|224|System Register Write|Stack Point Register Write||SRSPW|O1||SPR = Rd|�t���O�𔭐����Ȃ�|||||||
|0E1|225||Page Directory Table Register Write||SRPDTW|O1|||�t���O�𔭐����Ȃ�|||�J�[�l�����[�h�̂ݎ��s�\||�����ᔽ||
|0E5|229||Interrupt Enable Information Write||SRIEIW|O1|I11|mask(SR1) = (Rs & 0x00000004) >> 2|�t���O�𔭐����Ȃ�|||���[�g���[�h�̂ݎ��s�\|3|�����ᔽ|1�ŋ���|
|0E8|232||TISR Write ||SRTISW|O1||TISPR = Rd|�t���O�𔭐����Ȃ�|||���[�g���[�h�̂ݎ��s�\|3|�����ᔽ||
|0E9|233||KPDTR Write||SRKPDTW|O1||KPDTR = Rd|�t���O�𔭐����Ȃ�|||���[�g���[�h�̂ݎ��s�\|3|�����ᔽ||
|0EA|234||MMU Mode Write||SRMMUW|O1|I11|mask(SR1) = Rs & 0x00000011|�t���O�𔭐����Ȃ�|||���[�g���[�h�̂ݎ��s�\|3|�����ᔽ|0=�A�h���X�ϊ��Ȃ�, 1=�\��, 2=1�i�ϊ�, 3=2�i�ϊ�|
|0ED|237||PPSR Write||SRPPSW|O1|||�t���O�𔭐����Ȃ�|||||||
|0EE|238||PPCR Write||SRPPCW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F0|240||PPDTR Write||SRPPDTW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F1|241||PTIDR Write||SRPTIDW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F2|242||IDTR Write||SRIDTW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F3|243||PSR Write||SRPSW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F4|244||{FRCLR, FRCHR} -> FRCR||SRFRCW|C|||�t���O�𔭐����Ȃ�|||||||
|0F5|245||FRCLR Write||SRFRCLW|O1|||�t���O�𔭐����Ȃ�|||||||
|0F6|246||FRCHR Write||SRFRCHW|O1|||�t���O�𔭐����Ȃ�|||||||
|0FF|255||SPR + Immediate|�����g���@2bit���V�t�g|SRSPWADD||CI16|SPR = SPR + signed immediate|�t���O�𔭐����Ȃ�|||||||
|100|256|Other|No Operation||NOP|C||No Operation|�t���O�𔭐����Ȃ�|||||||
|101|257||pipline is halt||HALT|C||Halt|�t���O�𔭐����Ȃ�|||kernel���[�h�̂ݎ��s�\|3|�����ᔽ||
|102|258||move data||MOVE|O2||Rd = Rs|�t���O�𔭐����Ȃ�|||||||
|103|259||Move Programm Counter + Offset|�����g���@2bit���V�t�g|MOVEPC|O2|I11|Rd = Rs(Signed) + PC|�t���O�𔭐����Ȃ�|||||||
|120|288|OS & Interrupt Support|Software Interrupt ||SWI||I11|Software Interrupt, Interrupt Vector:Mask8bit(Rs)|�t���O�𔭐����Ȃ�|||||||
|121|289||Test And Set||TAS|O2|I11|tas gr[src0], mem[src1]|�t���O�𔭐����Ȃ�|||||||
|122|290||IDT Set||IDTS|C||Set IDT|�t���O�𔭐����Ȃ�|||�J�[�l�����[�h�̂�||�����ᔽ|IDTR�̏������ƂɃn�[�h�E�F�A���荞�݂̏���������W�X�^�ɑޔ�|
|123|291||Load Linked||LDL|||||||||||
|124|292||Store Conditional||STC|||||||||||
