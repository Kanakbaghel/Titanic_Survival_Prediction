{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "6528ddec",
   "metadata": {
    "_cell_guid": "b1076dfc-b9ad-4769-8c92-a6c4dae69d19",
    "_uuid": "8f2839f25d086af736a60e9eeb907d3b93b6e0e5",
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:17.674608Z",
     "iopub.status.busy": "2025-09-27T15:54:17.674245Z",
     "iopub.status.idle": "2025-09-27T15:54:19.948484Z",
     "shell.execute_reply": "2025-09-27T15:54:19.947446Z"
    },
    "papermill": {
     "duration": 2.283829,
     "end_time": "2025-09-27T15:54:19.950410",
     "exception": false,
     "start_time": "2025-09-27T15:54:17.666581",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "/kaggle/input/titanic-dataset/Titanic-Dataset.csv\n"
     ]
    }
   ],
   "source": [
    "# This Python 3 environment comes with many helpful analytics libraries installed\n",
    "# It is defined by the kaggle/python Docker image: https://github.com/kaggle/docker-python\n",
    "# For example, here's several helpful packages to load\n",
    "\n",
    "import numpy as np # linear algebra\n",
    "import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)\n",
    "\n",
    "# Input data files are available in the read-only \"../input/\" directory\n",
    "# For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory\n",
    "\n",
    "import os\n",
    "for dirname, _, filenames in os.walk('/kaggle/input'):\n",
    "    for filename in filenames:\n",
    "        print(os.path.join(dirname, filename))\n",
    "\n",
    "# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using \"Save & Run All\" \n",
    "# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b7e9f803",
   "metadata": {
    "papermill": {
     "duration": 0.00514,
     "end_time": "2025-09-27T15:54:19.961141",
     "exception": false,
     "start_time": "2025-09-27T15:54:19.956001",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "-------------------------\n",
    "<font size = 5 color = lightblue ><b> Importing Dataset into the Notebook\n",
    "\n",
    "------------------------"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "ea754b24",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:19.972859Z",
     "iopub.status.busy": "2025-09-27T15:54:19.972469Z",
     "iopub.status.idle": "2025-09-27T15:54:20.001294Z",
     "shell.execute_reply": "2025-09-27T15:54:20.000176Z"
    },
    "papermill": {
     "duration": 0.036841,
     "end_time": "2025-09-27T15:54:20.003214",
     "exception": false,
     "start_time": "2025-09-27T15:54:19.966373",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# importing dataset\n",
    "df = pd.read_csv('/kaggle/input/titanic-dataset/Titanic-Dataset.csv')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "1b00ddf2",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.015255Z",
     "iopub.status.busy": "2025-09-27T15:54:20.014886Z",
     "iopub.status.idle": "2025-09-27T15:54:20.047591Z",
     "shell.execute_reply": "2025-09-27T15:54:20.046553Z"
    },
    "papermill": {
     "duration": 0.040495,
     "end_time": "2025-09-27T15:54:20.049242",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.008747",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C85</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>C123</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Cabin Embarked  \n",
       "0      0         A/5 21171   7.2500   NaN        S  \n",
       "1      0          PC 17599  71.2833   C85        C  \n",
       "2      0  STON/O2. 3101282   7.9250   NaN        S  \n",
       "3      0            113803  53.1000  C123        S  \n",
       "4      0            373450   8.0500   NaN        S  "
      ]
     },
     "execution_count": 3,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Snapshot of the dataset\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "618a7828",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.061816Z",
     "iopub.status.busy": "2025-09-27T15:54:20.061476Z",
     "iopub.status.idle": "2025-09-27T15:54:20.070845Z",
     "shell.execute_reply": "2025-09-27T15:54:20.069613Z"
    },
    "papermill": {
     "duration": 0.017593,
     "end_time": "2025-09-27T15:54:20.072544",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.054951",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Shape\t\t: (891, 12)\n",
      "Row Labels\t: RangeIndex(start=0, stop=891, step=1)\n",
      "\n",
      "Column Labels:\n",
      " Index(['PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp',\n",
      "       'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked'],\n",
      "      dtype='object')\n",
      "\n",
      "Column Data Types:\n",
      " PassengerId      int64\n",
      "Survived         int64\n",
      "Pclass           int64\n",
      "Name            object\n",
      "Sex             object\n",
      "Age            float64\n",
      "SibSp            int64\n",
      "Parch            int64\n",
      "Ticket          object\n",
      "Fare           float64\n",
      "Cabin           object\n",
      "Embarked        object\n",
      "dtype: object\n"
     ]
    }
   ],
   "source": [
    "# Check out the Structure/info about the data\n",
    "print(f'Shape\\t\\t: {df.shape}')\n",
    "print(f'Row Labels\\t: {df.index}')\n",
    "print(f'\\nColumn Labels:\\n {df.columns}')\n",
    "print(f'\\nColumn Data Types:\\n {df.dtypes}')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "ab84635f",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.084901Z",
     "iopub.status.busy": "2025-09-27T15:54:20.084623Z",
     "iopub.status.idle": "2025-09-27T15:54:20.112428Z",
     "shell.execute_reply": "2025-09-27T15:54:20.111148Z"
    },
    "papermill": {
     "duration": 0.035976,
     "end_time": "2025-09-27T15:54:20.114208",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.078232",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 891 entries, 0 to 890\n",
      "Data columns (total 12 columns):\n",
      " #   Column       Non-Null Count  Dtype  \n",
      "---  ------       --------------  -----  \n",
      " 0   PassengerId  891 non-null    int64  \n",
      " 1   Survived     891 non-null    int64  \n",
      " 2   Pclass       891 non-null    int64  \n",
      " 3   Name         891 non-null    object \n",
      " 4   Sex          891 non-null    object \n",
      " 5   Age          714 non-null    float64\n",
      " 6   SibSp        891 non-null    int64  \n",
      " 7   Parch        891 non-null    int64  \n",
      " 8   Ticket       891 non-null    object \n",
      " 9   Fare         891 non-null    float64\n",
      " 10  Cabin        204 non-null    object \n",
      " 11  Embarked     889 non-null    object \n",
      "dtypes: float64(2), int64(5), object(5)\n",
      "memory usage: 83.7+ KB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "attachments": {
    "b33cced8-f02a-4467-8d07-4260e0280825.png": {
     "image/png": "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"
    }
   },
   "cell_type": "markdown",
   "id": "a04a1957",
   "metadata": {
    "papermill": {
     "duration": 0.005317,
     "end_time": "2025-09-27T15:54:20.125464",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.120147",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "<font size = 4 color = orange ><b> Detect Missing Values"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "dabce33d",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.138518Z",
     "iopub.status.busy": "2025-09-27T15:54:20.138206Z",
     "iopub.status.idle": "2025-09-27T15:54:20.158886Z",
     "shell.execute_reply": "2025-09-27T15:54:20.157702Z"
    },
    "papermill": {
     "duration": 0.029752,
     "end_time": "2025-09-27T15:54:20.160594",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.130842",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>886</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>887</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>888</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>889</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>890</th>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>891 rows × 12 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "     PassengerId  Survived  Pclass   Name    Sex    Age  SibSp  Parch  Ticket  \\\n",
       "0          False     False   False  False  False  False  False  False   False   \n",
       "1          False     False   False  False  False  False  False  False   False   \n",
       "2          False     False   False  False  False  False  False  False   False   \n",
       "3          False     False   False  False  False  False  False  False   False   \n",
       "4          False     False   False  False  False  False  False  False   False   \n",
       "..           ...       ...     ...    ...    ...    ...    ...    ...     ...   \n",
       "886        False     False   False  False  False  False  False  False   False   \n",
       "887        False     False   False  False  False  False  False  False   False   \n",
       "888        False     False   False  False  False   True  False  False   False   \n",
       "889        False     False   False  False  False  False  False  False   False   \n",
       "890        False     False   False  False  False  False  False  False   False   \n",
       "\n",
       "      Fare  Cabin  Embarked  \n",
       "0    False   True     False  \n",
       "1    False  False     False  \n",
       "2    False   True     False  \n",
       "3    False  False     False  \n",
       "4    False   True     False  \n",
       "..     ...    ...       ...  \n",
       "886  False   True     False  \n",
       "887  False  False     False  \n",
       "888  False   True     False  \n",
       "889  False  False     False  \n",
       "890  False   True     False  \n",
       "\n",
       "[891 rows x 12 columns]"
      ]
     },
     "execution_count": 6,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.isna() #returns True or False for each value"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "id": "b48198cf",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.174329Z",
     "iopub.status.busy": "2025-09-27T15:54:20.173988Z",
     "iopub.status.idle": "2025-09-27T15:54:20.183011Z",
     "shell.execute_reply": "2025-09-27T15:54:20.181948Z"
    },
    "papermill": {
     "duration": 0.018154,
     "end_time": "2025-09-27T15:54:20.184898",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.166744",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "PassengerId      0\n",
       "Survived         0\n",
       "Pclass           0\n",
       "Name             0\n",
       "Sex              0\n",
       "Age            177\n",
       "SibSp            0\n",
       "Parch            0\n",
       "Ticket           0\n",
       "Fare             0\n",
       "Cabin          687\n",
       "Embarked         2\n",
       "dtype: int64"
      ]
     },
     "execution_count": 7,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.isna().sum(axis=0) #column-wise sum"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "d9fe408e",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.198721Z",
     "iopub.status.busy": "2025-09-27T15:54:20.198365Z",
     "iopub.status.idle": "2025-09-27T15:54:20.205808Z",
     "shell.execute_reply": "2025-09-27T15:54:20.204570Z"
    },
    "papermill": {
     "duration": 0.016509,
     "end_time": "2025-09-27T15:54:20.207820",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.191311",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Replacing missing values under Age column with the median \n",
    "df.fillna(df['Age'].median(), inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "a5dffcf5",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.221188Z",
     "iopub.status.busy": "2025-09-27T15:54:20.220796Z",
     "iopub.status.idle": "2025-09-27T15:54:20.231499Z",
     "shell.execute_reply": "2025-09-27T15:54:20.229987Z"
    },
    "papermill": {
     "duration": 0.0197,
     "end_time": "2025-09-27T15:54:20.233512",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.213812",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Drop the Cabin column for data quality + model utility\n",
    "df.drop('Cabin', axis=1, inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "25146ef0",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.248601Z",
     "iopub.status.busy": "2025-09-27T15:54:20.248234Z",
     "iopub.status.idle": "2025-09-27T15:54:20.254931Z",
     "shell.execute_reply": "2025-09-27T15:54:20.253696Z"
    },
    "papermill": {
     "duration": 0.01721,
     "end_time": "2025-09-27T15:54:20.256975",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.239765",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Replacing Missing values of Embarked with mode\n",
    "df.fillna(df['Embarked'].mode()[0], inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "id": "0e905951",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.271435Z",
     "iopub.status.busy": "2025-09-27T15:54:20.270965Z",
     "iopub.status.idle": "2025-09-27T15:54:20.279335Z",
     "shell.execute_reply": "2025-09-27T15:54:20.278170Z"
    },
    "papermill": {
     "duration": 0.017653,
     "end_time": "2025-09-27T15:54:20.281210",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.263557",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "PassengerId    0\n",
       "Survived       0\n",
       "Pclass         0\n",
       "Name           0\n",
       "Sex            0\n",
       "Age            0\n",
       "SibSp          0\n",
       "Parch          0\n",
       "Ticket         0\n",
       "Fare           0\n",
       "Embarked       0\n",
       "dtype: int64"
      ]
     },
     "execution_count": 11,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Recheck the Values \n",
    "df.isna().sum(axis=0)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "55d7082d",
   "metadata": {
    "papermill": {
     "duration": 0.005864,
     "end_time": "2025-09-27T15:54:20.294208",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.288344",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "---------------\n",
    "<font size = 5 color = lightblue ><b> Feature Engineering\n",
    "\n",
    "-----------------"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "84b5bab2",
   "metadata": {
    "papermill": {
     "duration": 0.00632,
     "end_time": "2025-09-27T15:54:20.306564",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.300244",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "**Name column mein \"Mr.\", \"Miss\", \"Dr.\" jaise titles hote hain. Ye social status ya gender ka signal de sakte hain—jo survival ke chances ko affect karta hai.******"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "id": "82097750",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.321068Z",
     "iopub.status.busy": "2025-09-27T15:54:20.320242Z",
     "iopub.status.idle": "2025-09-27T15:54:20.336870Z",
     "shell.execute_reply": "2025-09-27T15:54:20.335701Z"
    },
    "papermill": {
     "duration": 0.026107,
     "end_time": "2025-09-27T15:54:20.339081",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.312974",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Embarked</th>\n",
       "      <th>Title</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C</td>\n",
       "      <td>Mrs</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>S</td>\n",
       "      <td>Miss</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>S</td>\n",
       "      <td>Mrs</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Embarked Title  \n",
       "0      0         A/5 21171   7.2500        S    Mr  \n",
       "1      0          PC 17599  71.2833        C   Mrs  \n",
       "2      0  STON/O2. 3101282   7.9250        S  Miss  \n",
       "3      0            113803  53.1000        S   Mrs  \n",
       "4      0            373450   8.0500        S    Mr  "
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Extraction of Title\n",
    "df['Title'] = df['Name'].str.extract(' ([A-Za-z]+)\\.', expand=False)\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "f0134d9a",
   "metadata": {
    "papermill": {
     "duration": 0.00595,
     "end_time": "2025-09-27T15:54:20.351482",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.345532",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "**Ek passenger ke saath kitne family members travel kar rahe hain—ye survival ke liye important ho sakta hai (group effect).**"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "id": "6b44030d",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.366789Z",
     "iopub.status.busy": "2025-09-27T15:54:20.366312Z",
     "iopub.status.idle": "2025-09-27T15:54:20.385445Z",
     "shell.execute_reply": "2025-09-27T15:54:20.384241Z"
    },
    "papermill": {
     "duration": 0.029193,
     "end_time": "2025-09-27T15:54:20.387333",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.358140",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Embarked</th>\n",
       "      <th>Title</th>\n",
       "      <th>FamilySize</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "      <td>2</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C</td>\n",
       "      <td>Mrs</td>\n",
       "      <td>2</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>S</td>\n",
       "      <td>Miss</td>\n",
       "      <td>1</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>S</td>\n",
       "      <td>Mrs</td>\n",
       "      <td>2</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "      <td>1</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Embarked Title  FamilySize  \n",
       "0      0         A/5 21171   7.2500        S    Mr           2  \n",
       "1      0          PC 17599  71.2833        C   Mrs           2  \n",
       "2      0  STON/O2. 3101282   7.9250        S  Miss           1  \n",
       "3      0            113803  53.1000        S   Mrs           2  \n",
       "4      0            373450   8.0500        S    Mr           1  "
      ]
     },
     "execution_count": 13,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Combination for family size\n",
    "df['FamilySize'] = df['SibSp'] + df['Parch'] + 1\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "513e0876",
   "metadata": {
    "papermill": {
     "duration": 0.006319,
     "end_time": "2025-09-27T15:54:20.400404",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.394085",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "**Akele travel karne wale logon ka survival pattern alag ho sakta hai.**"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "id": "14dc9f86",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.414754Z",
     "iopub.status.busy": "2025-09-27T15:54:20.414466Z",
     "iopub.status.idle": "2025-09-27T15:54:20.431183Z",
     "shell.execute_reply": "2025-09-27T15:54:20.430164Z"
    },
    "papermill": {
     "duration": 0.025821,
     "end_time": "2025-09-27T15:54:20.432797",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.406976",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Embarked</th>\n",
       "      <th>Title</th>\n",
       "      <th>FamilySize</th>\n",
       "      <th>IsAlone</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "      <td>2</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C</td>\n",
       "      <td>Mrs</td>\n",
       "      <td>2</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>S</td>\n",
       "      <td>Miss</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>S</td>\n",
       "      <td>Mrs</td>\n",
       "      <td>2</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>S</td>\n",
       "      <td>Mr</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Embarked Title  FamilySize  IsAlone  \n",
       "0      0         A/5 21171   7.2500        S    Mr           2        0  \n",
       "1      0          PC 17599  71.2833        C   Mrs           2        0  \n",
       "2      0  STON/O2. 3101282   7.9250        S  Miss           1        1  \n",
       "3      0            113803  53.1000        S   Mrs           2        0  \n",
       "4      0            373450   8.0500        S    Mr           1        1  "
      ]
     },
     "execution_count": 14,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Flagging (Binary indicators)\n",
    "df['IsAlone'] = (df['FamilySize'] == 1).astype(int)\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7b877354",
   "metadata": {
    "papermill": {
     "duration": 0.006301,
     "end_time": "2025-09-27T15:54:20.445966",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.439665",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "--------------------\n",
    "<font size = 5 color = lightblue><b> Exploratory Data Analysis\n",
    "\n",
    "---------------------"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "fcfc49a5",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.460745Z",
     "iopub.status.busy": "2025-09-27T15:54:20.460448Z",
     "iopub.status.idle": "2025-09-27T15:54:20.498161Z",
     "shell.execute_reply": "2025-09-27T15:54:20.496175Z"
    },
    "papermill": {
     "duration": 0.047932,
     "end_time": "2025-09-27T15:54:20.500645",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.452713",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Shape of the dataset\t\t: (891, 14)\n",
      "\n",
      "Columns in the Data\n",
      " : Index(['PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp',\n",
      "       'Parch', 'Ticket', 'Fare', 'Embarked', 'Title', 'FamilySize',\n",
      "       'IsAlone'],\n",
      "      dtype='object')\n",
      "\n",
      "Data Types\n",
      " : PassengerId      int64\n",
      "Survived         int64\n",
      "Pclass           int64\n",
      "Name            object\n",
      "Sex             object\n",
      "Age            float64\n",
      "SibSp            int64\n",
      "Parch            int64\n",
      "Ticket          object\n",
      "Fare           float64\n",
      "Embarked        object\n",
      "Title           object\n",
      "FamilySize       int64\n",
      "IsAlone          int64\n",
      "dtype: object\n",
      "\n",
      "Overview of the Data:\n",
      "        PassengerId    Survived      Pclass         Age       SibSp  \\\n",
      "count   891.000000  891.000000  891.000000  891.000000  891.000000   \n",
      "mean    446.000000    0.383838    2.308642   29.361582    0.523008   \n",
      "std     257.353842    0.486592    0.836071   13.019697    1.102743   \n",
      "min       1.000000    0.000000    1.000000    0.420000    0.000000   \n",
      "25%     223.500000    0.000000    2.000000   22.000000    0.000000   \n",
      "50%     446.000000    0.000000    3.000000   28.000000    0.000000   \n",
      "75%     668.500000    1.000000    3.000000   35.000000    1.000000   \n",
      "max     891.000000    1.000000    3.000000   80.000000    8.000000   \n",
      "\n",
      "            Parch        Fare  FamilySize     IsAlone  \n",
      "count  891.000000  891.000000  891.000000  891.000000  \n",
      "mean     0.381594   32.204208    1.904602    0.602694  \n",
      "std      0.806057   49.693429    1.613459    0.489615  \n",
      "min      0.000000    0.000000    1.000000    0.000000  \n",
      "25%      0.000000    7.910400    1.000000    0.000000  \n",
      "50%      0.000000   14.454200    1.000000    1.000000  \n",
      "75%      0.000000   31.000000    2.000000    1.000000  \n",
      "max      6.000000  512.329200   11.000000    1.000000  \n",
      "\n",
      "Empty Data:\n",
      " PassengerId    0\n",
      "Survived       0\n",
      "Pclass         0\n",
      "Name           0\n",
      "Sex            0\n",
      "Age            0\n",
      "SibSp          0\n",
      "Parch          0\n",
      "Ticket         0\n",
      "Fare           0\n",
      "Embarked       0\n",
      "Title          0\n",
      "FamilySize     0\n",
      "IsAlone        0\n",
      "dtype: int64\n"
     ]
    }
   ],
   "source": [
    "## Check out the dataset\n",
    "print(f'Shape of the dataset\\t\\t: {df.shape}')\n",
    "print(f'\\nColumns in the Data\\n : {df.columns}')\n",
    "print(f'\\nData Types\\n : {df.dtypes}')\n",
    "print(f'\\nOverview of the Data:\\n {df.describe()}')\n",
    "print(f'\\nEmpty Data:\\n {df.isna().sum().sort_values(ascending=False)}')"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "a42a2764",
   "metadata": {
    "papermill": {
     "duration": 0.006814,
     "end_time": "2025-09-27T15:54:20.514710",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.507896",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "--------------------\n",
    "### Univariate Analysis (Distribution)\n",
    "\n",
    "------------------------"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "b22a75b4",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2025-09-27T15:54:20.530689Z",
     "iopub.status.busy": "2025-09-27T15:54:20.530368Z",
     "iopub.status.idle": "2025-09-27T15:54:20.534961Z",
     "shell.execute_reply": "2025-09-27T15:54:20.534032Z"
    },
    "papermill": {
     "duration": 0.014637,
     "end_time": "2025-09-27T15:54:20.536881",
     "exception": false,
     "start_time": "2025-09-27T15:54:20.522244",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# "
   ]
  }
 ],
 "metadata": {
  "kaggle": {
   "accelerator": "none",
   "dataSources": [
    {
     "datasetId": 1818188,
     "sourceId": 2965537,
     "sourceType": "datasetVersion"
    }
   ],
   "dockerImageVersionId": 31089,
   "isGpuEnabled": false,
   "isInternetEnabled": true,
   "language": "python",
   "sourceType": "notebook"
  },
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.13"
  },
  "papermill": {
   "default_parameters": {},
   "duration": 9.689891,
   "end_time": "2025-09-27T15:54:21.066082",
   "environment_variables": {},
   "exception": null,
   "input_path": "__notebook__.ipynb",
   "output_path": "__notebook__.ipynb",
   "parameters": {},
   "start_time": "2025-09-27T15:54:11.376191",
   "version": "2.6.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
