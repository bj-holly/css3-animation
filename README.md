# css3-animation

<pre>

CSS3������������Ҫ��Ϊ���ࣺtransform��transition�Լ�animation��

һ��transform

	1��rotate		����Ԫ��˳ʱ����ת�ĽǶȣ��÷��ǣ�
			
					transform: rotate(x);		����x��������deg��β�ĽǶ�����0����Ϊ������ʾ����

	2��scale		����Ԫ�طŴ����С�ı������÷�������

					transform: scale(a);		Ԫ��x��y���������a��
					transform: scale(a, b);	Ԫ��x��������a����y��������b��
					transform: scaleX(a);		Ԫ��x��������a����y���򲻱�
					transform: scaleY(b);		Ԫ��y��������b����x���򲻱�
	
	3��translate	����Ԫ�ص�λ�ƣ��÷�������

					transform: translate(a, b);		Ԫ��x����λ��a��y����λ��b
					transform: translateX(a);		Ԫ��x����λ��a��y���򲻱�
					transform: translateY(b);		Ԫ��y����λ��b��x���򲻱�

	4��skew			����Ԫ����б�ĽǶȣ��÷�������

					transform: skew(a, b);	Ԫ��x������ʱ����б�Ƕ�a��y����˳ʱ����б�Ƕ�b
					transform: skewX(a);		Ԫ��x������ʱ����б�Ƕ�a��y���򲻱�
					transform: skewY(b);		Ԫ��y����˳ʱ����б�Ƕ�b���뷽�򲻱�
											���ϵĲ�������������deg��β�ĽǶ�����0����Ϊ������ʾ����

	5��matrix		����Ԫ�صı��ξ�����Ϊ������ι��ڸ��ӣ����ԡ�
	
	6��origin		����Ԫ�ص����ҵ㣬�÷�������

					transform-origin: a b;	Ԫ�ص����ҵ�Ϊ(a, b)
											Ԫ�ص����ҵ㼴Ϊ����ת����бʱ�����ĵ㡣ȡֵ�е�a��b�����ǳ���ֵ����%��β�İٷֱȻ���left��top��right��bottom�ĸ�ֵ��


����transition

	1��transition-property			ָ��transitionЧ�����õ�CSS���ԣ���ֵ��CSS��������
	2��transition-duration			����Ч��������ʱ�䣬��ֵΪ��s��β��������
	3��transition-timing-function		ָ��Ԫ��״̬�ı仯���ʺ�������ȡֵ���ڱ��������ߺ�����
	4��transition-delay				����Ч���Ƴٿ�ʼִ�е�ʱ�䣬��ֵΪ��s��β��������
									PS��transition: property duration timing-function delay;
									
									transition-timing-function:
									linear		�涨����ͬ�ٶȿ�ʼ�������Ĺ���Ч�������� cubic-bezier(0,0,1,1)����
									ease		�涨���ٿ�ʼ��Ȼ���죬Ȼ�����ٽ����Ĺ���Ч����cubic-bezier(0.25,0.1,0.25,1)����
									ease-in		�涨�����ٿ�ʼ�Ĺ���Ч�������� cubic-bezier(0.42,0,1,1)����
									ease-out	�涨�����ٽ����Ĺ���Ч�������� cubic-bezier(0,0,0.58,1)����
									ease-in-out	�涨�����ٿ�ʼ�ͽ����Ĺ���Ч�������� cubic-bezier(0.42,0,0.58,1)����
									cubic-bezier(n,n,n,n)	�� cubic-bezier �����ж����Լ���ֵ�����ܵ�ֵ�� 0 �� 1 ֮�����ֵ��


����animation	CSS3�������Ķ���������animation����ǰ���transform��transition��ֻ�Ƕ�DOMԪ�صı��λ�����״̬�Ĺ��ɡ�ʵ���ϣ�CSS3��֧�ֵĶ���Ч��ֻ����䶯����Ҳ����˵���趨�����������������еļ����ؼ�״̬��key  frame���ؼ�֡����Ȼ�󶯻������м��㲢ģ��ؼ�֮֡��Ĺ��ɡ���ô������animation������֮ǰ�ͱ������趨�ùؼ�֡�ˡ�
	

	1��@keyframes name{

			a% {
		         /*CSS����*/
	         }

		    b% {
				/*CSS����*/
			}
			...
		}

	2��animation					���ж������Եļ�д���ԣ����� animation-play-state ���ԡ�		
	
	3��animation-name				�涨 @keyframes ���������ơ�
	
	4��animation-duration			�涨�������һ�����������ѵ������롣Ĭ���� 0��
	
	5��animation-timing-function	�涨�������ٶ����ߡ�Ĭ���� "ease"��
									linear	������ͷ��β���ٶ�����ͬ�ġ�	
									ease	Ĭ�ϡ������Ե��ٿ�ʼ��Ȼ��ӿ죬�ڽ���ǰ������
									ease-in	�����Ե��ٿ�ʼ��	
									ease-out	�����Ե��ٽ�����	
									ease-in-out	�����Ե��ٿ�ʼ�ͽ�����	
									cubic-bezier(n,n,n,n)	�� cubic-bezier �������Լ���ֵ�����ܵ�ֵ�Ǵ� 0 �� 1 ����ֵ��

	6��animation-delay				�涨������ʱ��ʼ��Ĭ���� 0��

	7��animation-iteration-count	�涨���������ŵĴ�����Ĭ���� 1��
									n	���嶯�����Ŵ�������ֵ��	
									infinite	�涨����Ӧ�����޴β��š�

	8��animation-direction			�涨�����Ƿ�����һ��������ز��š�Ĭ���� "normal"��
									normal	Ĭ��ֵ������Ӧ���������š�	
									alternate	����Ӧ���������򲥷š�
	
	9��animation-play-state			�涨�����Ƿ��������л���ͣ��Ĭ���� "running"���������� JavaScript ��ʹ�ø����ԣ����������ڲ��Ź�������ͣ������
									paused	�涨��������ͣ��
									running	�涨�������ڲ��š�
									
	10��animation-fill-mode			�涨���󶯻�ʱ��֮���״̬��
									forwards	��������ɺ󣬱������һ������ֵ�������һ���ؼ�֡�ж��壩��
									backwards	�� animation-delay ��ָ����һ��ʱ���ڣ��ڶ�����ʾ֮ǰ��Ӧ�ÿ�ʼ����ֵ���ڵ�һ���ؼ�֡�ж��壩��
									both	��ǰ��������ģʽ����Ӧ�á�
				

�ġ�ǰ׺

	��ΪCSS3��û����ʽ���������Ը��������������֧��Ҳ������ͬ��
	����������CSS3���ԣ�����@��ͷ�������ԣ���ʱ��ͨ����Ҫ��������������ʶ��ǰ׺��
	-webkit- ��ʾWebkit�ں˵������Chrome��Safari��
	-moz- ��ʾFireFox��
	-o- ��ʾOpera��
	����IE�ɣ���IE�ϵ�ʵ��ͨ������Ҫ�õ��˾���������CSS3��

</pre>