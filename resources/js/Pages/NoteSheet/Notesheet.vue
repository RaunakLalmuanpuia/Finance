<template>
    <QuasarLayout>
        
        <p>Rich Text Editor</p>
        
            <Editor
                api-key="4n17cx9dey2slrri7v0vko1hv6sho7bzzrcsgfa243xshsks"
                :disabled=false
                :init="{
                    toolbar_mode: 'sliding',
                    plugins: 'ai tinycomments mentions anchor autolink charmap codesample emoticons image link lists media searchreplace table visualblocks wordcount checklist mediaembed casechange export formatpainter pageembed permanentpen footnotes advtemplate advtable advcode editimage tableofcontents mergetags powerpaste tinymcespellchecker autocorrect a11ychecker typography inlinecss',
                    toolbar: 'undo redo | blocks fontfamily fontsize | bold italic underline strikethrough | link image media table mergetags | align lineheight | tinycomments | checklist numlist bullist indent outdent | emoticons charmap | removeformat',
                    tinycomments_mode: 'embedded',
                    tinycomments_author: 'Author name',
                    // mergetags_list: [
                    // { value: 'First.Name', title: 'First Name' },
                    // { value: 'Email', title: 'Email' }
                    // ],
                    ai_request: (request, respondWith) => respondWith.string(() => Promise.reject('See docs to implement AI Assistant'))
                }"
                v-model="Docx"
            />
    </QuasarLayout>
</template>

<script setup >


import QuasarLayout from '@/Layouts/QuasarLayout.vue';
// import vuequilleditor from 'vue-quill-editor';
import {ref} from 'vue'
import Editor from '@tinymce/tinymce-vue'
import { usePage } from '@inertiajs/vue3';

const page = usePage();
const props = defineProps({
    'name' : String,
    'id': String,
    'peroid': String,
    'amount' : String,
})
const varValue = page.props.id;
const Docx = ref(`<p>&nbsp;</p>\n<p style="text-align: center;">ID NO Fin ${varValue}</p>\n<p style="text-align: center;">This is a Proposal for Expenditure Sanction amounting to ${page.props.amount} {#Amount in words#} during ${page.props.peroid}</p>\n<p style="text-align: center;">under ${props.name}.</p>\n<p style="text-align: center;">The Expenditure is debited under the head of account:</p>\n<p style="text-align: center;">{#All Head of Account#}</p>\n<p style="text-align: center;">Fund Position</p>\n<table style="border-collapse: collapse; width: 48.0769%; height: 30.4px; border-width: 5px; border-style: solid;" border="1"><colgroup><col style="width: 21.9412%;"><col style="width: 28.0281%;"><col style="width: 25.0554%;"><col style="width: 24.9139%;"></colgroup>\n<tbody>\n<tr style="height: 30.4px;">\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n</tr>\n</tbody>\n</table>`);
// const Docx = ref('<p>&nbsp;</p>\n<p style="text-align: center;">ID NO Fin ${varValue}</p>\n<p style="text-align: center;">This is a Proposal for Expenditure Sanction amounting to {#Amount#} {#Amount in words#} during {#period#}</p>\n<p style="text-align: center;">under {#Project Name#}.</p>\n<p style="text-align: center;">The Expenditure is debited under the head of account:</p>\n<p style="text-align: center;">{#All Head of Account#}</p>\n<p style="text-align: center;">Fund Position</p>\n<table style="border-collapse: collapse; width: 48.0769%; height: 30.4px; border-width: 5px; border-style: solid;" border="1"><colgroup><col style="width: 21.9412%;"><col style="width: 28.0281%;"><col style="width: 25.0554%;"><col style="width: 24.9139%;"></colgroup>\n<tbody>\n<tr style="height: 30.4px;">\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n<td style="border-width: 5px; height: 30.4px;">&nbsp;</td>\n</tr>\n</tbody>\n</table>');
</script>
