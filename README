@Author Abdulhakim Haliru
@www.leproghrammeen.com
@http://www.hakim-haliru.blogspot.com
@Here I am Complying to RESTful patterns
@Oct. 1, 2012
/* Live Demo visit http://www.sosairen.org */
1. Copy 'CaptchaComponent.php' file to your /app/Controller/Component directory

2. add  'Captcha'  into your component variable inside the controller where you want to use it.

3. go to the controller action where  you would want to use the captcha and call component methods [__init(),first_number(),second_number()].

e.g.

<?php
App::uses('AppController', 'Controller');
class DummiesController extends AppController
{
  var public $components=array('Captcha');
	function foobar()
	{

	if($this->request->is('post') )
	{
	if(((int) $this->Captcha->getFirst() + (int) $this->Captcha->getSecond()) == (int) $this->request->data['Dummy']['captcha_result']) 
	{
	....your code logic
	}
	else
	{
	$this->Session->setFlash('oops, You are perhaps a bot! :p');
	exit;
	}
	}
	elseif($this->request->is('get')
	{
	// Here Your printing Captcha Value to Screen
	$this->Captcha->__init();
	$this->set('p', $this->Captcha->getFirst());
	$this->set('q', $this->Captcha->getSecond());
	}

	}

}
?>

/app/views/dummies/foobar.ctp

<?php 
echo $this->Form->create('Dummy',array('action'=>'foobar'));
echo $this->Form->label('What is the result of the sum of: ');
echo  $this->Form->input('Page.captcha_result' , array('label'=>$p .' + '. $q.' '));
                  
echo $this->Form->end());
?>
