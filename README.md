# IELTS Learning Assistant System

Enhanced RAG System with Dynamic Relevance Assessment for IELTS preparation.

## ��Ŀ����

IELTS Learning Assistant System��һ������ѧϰ���֣�������ǿ������ǿ����(RAG)������רΪIELTS������ơ�ϵͳͨ����̬������������ƣ��ṩ�߶���ص�ѧϰ��Դ�͸��Ի������������û���Ч������

## ϵͳ�ܹ�

ϵͳ��Ϊ������Ҫ���֣�

### 1. Ԥ����׶Σ����ߣ�

- **�ı������ռ�**������IELTS�̲ĺ�ѧϰ��Դ
- **���ӷָ�**��ʹ��spaCy���ı��ָ�Ϊ10�仰�������
- **Ƕ������**��ʹ��all-mpnet-base-v2ģ������768ά������ʾ
- **�����洢**����CSV��ʽ������������

### 2. ����������

- **�û���ѯ**�������û�����
- **��������**�����ڵ�����ƶȼ����������
- **���������ȡ**����ȡTop-5��������
- **���������**��ʹ��0.65��ֵ�������������
- **LLM����**��ʹ��Gemma-2b-itģ�����ɻش�
- **���չʾ**�����ִ𰸼����������

### 3. ���ӹ���

- **д������**�����ۺ͸Ľ�IELTS����
- **ѧϰ�ƻ�**�����ɸ��Ի�ѧϰ·��ͼ
- **ģ�����**���ṩIELTSģ������
- **�ı�ת����**��ʹ��MMS-TTS-Engת���ı�Ϊ����
- **���ȸ���**����¼ѧϰ���Ⱥ��ṩ����

## ��������

1. **��̬���������**������0.65��ֵ��̬�����ش����
2. **��ϸ�����Ϸֿ�**��10�仰Ϊ��λ�ķֿ����ƽ�������ĺ;���
3. **������ģ��ѡ��**��ʹ��Gemma-2b-it��֤�ٶȺ�����ƽ��
4. **��ģ̬����**������ı�����������֧�ֶ���ѧϰ��ʽ
5. **ѧϰ�ջ����**��ͨ�����ȸ��ٷ����Ż�ѧϰ�ƻ�

## ��װ˵��

### ����Ҫ��

- Python 3.8+
- PyTorch 1.12+
- Transformers 4.26+
- spaCy 3.5+

### ��װ����

1. ��¡�ֿ⣺
\\\ash
git clone https://github.com/�����û���/ielts-learning-assistant.git
cd ielts-learning-assistant
\\\

2. ��װ������
\\\ash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
\\\

3. ���ر�Ҫģ�ͣ�
\\\ash
python download_models.py
\\\

## ʹ�÷���

### Ԥ��������

\\\ash
python preprocessing/run_preprocessing.py --input_dir data/sample_texts --output_dir data/embeddings
\\\

### ����ϵͳ

\\\ash
python main.py
\\\

���� http://localhost:5000 ʹ��Web���档

### APIʹ��ʾ��

\\\python
from core.api import IELTSAssistant

assistant = IELTSAssistant()
response = assistant.ask("������IELTSд������?")
print(response)
\\\

## ��Ŀ�ṹ

\\\
ielts-learning-assistant/
������ preprocessing/       # Ԥ����׶δ���
������ core/                # �����̴���
������ features/            # ���ӹ��ܴ���
������ ui/                  # �û��������
������ data/                # ʾ������
������ models/              # ģ������
������ requirements.txt     # ��Ŀ����
������ main.py              # ���������
\\\

## �Ŷ���Ϣ

LEO, RAY, Daniella

## ���֤

MIT

## ��л

��лSentenceTransformer��Google Gemma��Facebook MMS-TTS-Eng�ṩ�ļ���֧�֡�
