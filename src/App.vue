<template>
  <div>
    <Loader></Loader>
    <Divider></Divider>
    <NavBar></NavBar>
    <NavLink></NavLink>
    <SearchBar></SearchBar>
    <LineChart></LineChart>
    <BarChart></BarChart>
    <CircleChart></CircleChart>
    <Pagination></Pagination>  
    <PageHeader></PageHeader>
    <Sidebar></Sidebar>
    <UserProfileImage></UserProfileImage>
    <DataPicker></DataPicker>
    <GridSystem></GridSystem>
    <Tab></Tab>
    <Text></Text>
    <Breadcrumb></Breadcrumb>
    <InputText></InputText>
    <InputEmail></InputEmail>
    <InputNumber></InputNumber>
    <InputPassword></InputPassword>
    <InputFile></InputFile>
    <DateTimePicker></DateTimePicker>
    <Breadcrumb></Breadcrumb>
    <FormSelect></FormSelect>
    <FormTextarea></FormTextarea>
    <FormCheckbox></FormCheckbox>
    <FormRadiobox></FormRadiobox>
    <FormToggle></FormToggle>
    <Button></Button>
    <DropdownButtons></DropdownButtons>
    <GroupButton></GroupButton>
    <Slider></Slider>
    <Forms></Forms>
    <Card></Card>
    <Accordion></Accordion>
    <Collapse></Collapse>
    <Label></Label>
    <ProgressBar></ProgressBar>
    <Tooltip></Tooltip>
    <MessageBox></MessageBox>
    <Modal></Modal>
    <Alert></Alert>
    <Icon></Icon>
    <Carousel></Carousel>
    <Table></Table>
    <List></List>
    <ListGroup></ListGroup>
    <Tags></Tags>
    <Image></Image>
    <Drawer></Drawer>
    <PageFooter></PageFooter>
    <LinkGroup></LinkGroup>
    
  </div>
</template>

<script>
  import InputText from './components/Inputs/InputText.vue';
  import InputEmail from './components/Inputs/InputEmail.vue';
  import InputPassword from './components/Inputs/InputPassword.vue';
  import InputNumber from './components/Inputs/InputNumber.vue';
  import InputFile from './components/Inputs/InputFile.vue';
  import DateTimePicker from './components/Inputs/DateTimePicker.vue';
  import FormSelect from './components/forms/FormSelect.vue';
  import FormTextarea from './components/forms/FormTextarea.vue';
  import FormCheckbox from './components/forms/FormCheckbox.vue';
  import FormRadiobox from './components/forms/FormRadiobox.vue';
  import FormToggle from './components/forms/FormToggle.vue';
  import Button from './components/buttons/Button.vue';
  import DropdownButtons from './components/buttons/DropdownButtons.vue';
  import GroupButton from './components/buttons/GroupButton.vue';
  import Slider from './components/slider/Sliders.vue';
  import Forms from './components/Froms.vue';
  import Card from './components/containers/Card.vue';
  import Accordion from './components/containers/Accordion.vue';
  import Collapse from './components/containers/Collapse.vue';
  import Label from './components/content/Label.vue';
  import ProgressBar from './components/content/ProgressBar.vue';
  import Tooltip from './components/content/Tooltip.vue';
  import MessageBox from './components/content/MessageBox.vue';
  import Modal from './components/content/Modal.vue';
  import Alert from './components/content/Alert.vue';
  import Icon from './components/content/Icons.vue';
  import Carousel from './components/content/ImagesCarousel.vue';
  import Table from './components/content/Table.vue';
  import List from './components/content/List.vue';
  import PageHeader from './components/content/PageHeader.vue';
  import PageFooter from './components/content/PageFooter.vue';
  import Sidebar from './components/content/Sidebar.vue';
  import NavBar from './components/navigation/NavBar.vue';
  import SearchBar from './components/navigation/SearchBar.vue';
  import Breadcrumb from './components/navigation/Breadcrumb.vue';
  import Pagination from './components/navigation/Pagination.vue';
  import Tags from './components/navigation/Tags.vue';
  import ListGroup from './components/navigation/ListGroup.vue';
  import NavLink from './components/navigation/NavLinks.vue';
  import LinkGroup from './components/navigation/LinkGroup.vue';
  import Tab from './components/navigation/Tabs.vue';
  import Drawer from './components/navigation/Drawers.vue';
  import Loader from './components/others/Loader.vue';
  import Divider from './components/others/Divider.vue';
  import Image from './components/others/Image.vue';
  import Text from './components/others/Text.vue';
  import UserProfileImage from './components/others/UserProfileImage.vue';
  import DataPicker from './components/others/DataPicker.vue';
  import GridSystem from './components/others/GridSystem.vue';
  import LineChart from './components/others/LineChart.vue';
  import BarChart from './components/others/BarChart.vue';
  import CircleChart from './components/others/CircleChart.vue';



  export default{
    components: {
      InputText,
      InputEmail,
      InputNumber,
      InputPassword,
      InputFile,
      DateTimePicker,
      FormSelect,
      FormTextarea,
      FormCheckbox,
      FormRadiobox,
      FormToggle,
      Button,
      DropdownButtons,
      GroupButton,
      Slider,
      Forms,
      Card,
      Accordion,
      Collapse,
      Label,
      ProgressBar,
      Tooltip,
      MessageBox,
      Modal,
      Alert,
      Icon,
      Carousel,
      Table,
      List,
      PageHeader,
      PageFooter,
      Sidebar,
      NavBar,
      SearchBar,
      Breadcrumb,
      Pagination,
      Tags,
      ListGroup,
      NavLink,
      LinkGroup,
      Tab,
      Drawer,
      Loader,
      Divider,
      Image,
      Text,
      UserProfileImage,
      DataPicker,
      GridSystem,
      LineChart,
      BarChart,
      CircleChart
    },
    methods: {
    showAlert() {
      this.$refs.messageBox.showMessage('Hello, this is a message!');
    },
  },
  }
</script>

<style scoped>

</style>
